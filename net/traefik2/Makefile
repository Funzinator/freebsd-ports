# $FreeBSD$

PORTNAME=	traefik2
DISTVERSIONPREFIX=	v
DISTVERSION=	2.2.0
CATEGORIES=	net

MAINTAINER=	freebsd@funzi.org
COMMENT=	High availability reverse proxy and load balancer

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.md

USES=		go:modules

USE_GITHUB=	yes
GH_ACCOUNT=	containous
GH_PROJECT=	traefik
GH_SUBDIR=	src/github.com/containous/traefik

USE_RC_SUBR=	traefik

GO_BUILDFLAGS=	-ldflags "-s -w \
		-X github.com/containous/traefik/version.Version=${DISTVERSION} \
		-X github.com/containous/traefik/version.BuildDate=`date -u '+%Y-%m-%d_%I:%M:%S%p'`"
GO_TARGET=	./cmd/traefik
CGO_ENABLED=	0

USERS=		traefik
GROUPS=		traefik

GH_TUPLE=	\
		Azure:azure-sdk-for-go:v32.4.0:azure_azure_sdk_for_go/vendor/github.com/Azure/azure-sdk-for-go \
		Azure:go-ansiterm:d6e3b3328b78:azure_go_ansiterm/vendor/github.com/Azure/go-ansiterm \
		Azure:go-autorest:autorest/v0.1.0:azure_go_autorest/vendor/github.com/Azure/go-autorest/autorest/azure/auth \
		Azure:go-autorest:autorest/v0.1.0:azure_go_autorest_1/vendor/github.com/Azure/go-autorest/autorest/azure/cli \
		Azure:go-autorest:autorest/v0.1.0:azure_go_autorest_2/vendor/github.com/Azure/go-autorest/autorest/date \
		Azure:go-autorest:autorest/v0.1.0:azure_go_autorest_3/vendor/github.com/Azure/go-autorest/autorest/validation \
		Azure:go-autorest:autorest/v0.1.0:azure_go_autorest_4/vendor/github.com/Azure/go-autorest/logger \
		Azure:go-autorest:autorest/v0.2.0:azure_go_autorest_5/vendor/github.com/Azure/go-autorest/autorest/to \
		Azure:go-autorest:autorest/v0.5.0:azure_go_autorest_6/vendor/github.com/Azure/go-autorest/autorest/adal \
		Azure:go-autorest:autorest/v0.5.0:azure_go_autorest_7/vendor/github.com/Azure/go-autorest/tracing \
		Azure:go-autorest:autorest/v0.9.0:azure_go_autorest_8/vendor/github.com/Azure/go-autorest/autorest \
		BurntSushi:toml:v0.3.1:burntsushi_toml/vendor/github.com/BurntSushi/toml \
		DataDog:datadog-go:v2.2.0:datadog_datadog_go/vendor/github.com/DataDog/datadog-go \
		DataDog:dd-trace-go:v1.19.0:datadog_dd_trace_go/vendor/gopkg.in/DataDog/dd-trace-go.v1 \
		ExpediaDotCom:haystack-client-go:e7edbdf53a61:expediadotcom_haystack_client_go/vendor/github.com/ExpediaDotCom/haystack-client-go \
		Masterminds:goutils:v1.1.0:masterminds_goutils/vendor/github.com/Masterminds/goutils \
		Masterminds:semver:v1.4.2:masterminds_semver/vendor/github.com/Masterminds/semver \
		Masterminds:sprig:v2.22.0:masterminds_sprig/vendor/github.com/Masterminds/sprig \
		Microsoft:go-winio:fc70bd9a86b5:microsoft_go_winio/vendor/github.com/Microsoft/go-winio \
		Microsoft:hcsshim:v0.8.7:microsoft_hcsshim/vendor/github.com/Microsoft/hcsshim \
		NYTimes:gziphandler:v1.1.1:nytimes_gziphandler/vendor/github.com/NYTimes/gziphandler \
		OpenDNS:vegadns2client:a3fa4a771d87:opendns_vegadns2client/vendor/github.com/OpenDNS/vegadns2client \
		PuerkitoBio:purell:v1.1.1:puerkitobio_purell/vendor/github.com/PuerkitoBio/purell \
		PuerkitoBio:urlesc:de5bf2ad4578:puerkitobio_urlesc/vendor/github.com/PuerkitoBio/urlesc \
		Shopify:sarama:v1.23.1:shopify_sarama/vendor/github.com/Shopify/sarama \
		VividCortex:gohistogram:v1.0.0:vividcortex_gohistogram/vendor/github.com/VividCortex/gohistogram \
		abronan:valkeyrie:ef4277a138cd:abronan_valkeyrie/vendor/github.com/abronan/valkeyrie \
		akamai:AkamaiOPEN-edgegrid-golang:v0.9.8:akamai_akamaiopen_edgegrid_golang/vendor/github.com/akamai/AkamaiOPEN-edgegrid-golang \
		aliyun:alibaba-cloud-sdk-go:07798873deee:aliyun_alibaba_cloud_sdk_go/vendor/github.com/aliyun/alibaba-cloud-sdk-go \
		armon:go-metrics:ec5e00d3c878:armon_go_metrics/vendor/github.com/armon/go-metrics \
		armon:go-radix:v1.0.0:armon_go_radix/vendor/github.com/armon/go-radix \
		aws:aws-sdk-go:v1.23.0:aws_aws_sdk_go/vendor/github.com/aws/aws-sdk-go \
		beorn7:perks:v1.0.1:beorn7_perks/vendor/github.com/beorn7/perks \
		c0va23:go-proxyprotocol:v0.9.1:c0va23_go_proxyprotocol/vendor/github.com/c0va23/go-proxyprotocol \
		cenkalti:backoff:v4.0.0:cenkalti_backoff/vendor/github.com/cenkalti/backoff/v4 \
		census-instrumentation:opencensus-go:v0.22.3:census_instrumentation_opencensus_go/vendor/go.opencensus.io \
		cloudflare:cloudflare-go:v0.10.2:cloudflare_cloudflare_go/vendor/github.com/cloudflare/cloudflare-go \
		codahale:hdrhistogram:3a0bb77429bd:codahale_hdrhistogram/vendor/github.com/codahale/hdrhistogram \
		containerd:containerd:v1.3.2:containerd_containerd/vendor/github.com/containerd/containerd \
		containerd:continuity:aaeac12a7ffc:containerd_continuity/vendor/github.com/containerd/continuity \
		containous:alice:d83ebdd94cbd:containous_alice/vendor/github.com/containous/alice \
		containous:check:ca0bf163426a:containous_check/vendor/github.com/go-check/check \
		containous:check:ca0bf163426a:containous_check_1/vendor/github.com/go-check/check \
		containous:go-http-auth:a37a7636d23e:containous_go_http_auth/vendor/github.com/abbot/go-http-auth \
		containous:go-http-auth:a37a7636d23e:containous_go_http_auth_1/vendor/github.com/abbot/go-http-auth \
		containous:minheap:6e71eb837595:containous_minheap/vendor/github.com/mailgun/minheap \
		containous:minheap:6e71eb837595:containous_minheap_1/vendor/github.com/mailgun/minheap \
		containous:multibuf:8b6c9a7e6bba:containous_multibuf/vendor/github.com/mailgun/multibuf \
		containous:multibuf:8b6c9a7e6bba:containous_multibuf_1/vendor/github.com/mailgun/multibuf \
		containous:mux:c33f32e26898:containous_mux/vendor/github.com/gorilla/mux \
		containous:mux:c33f32e26898:containous_mux_1/vendor/github.com/gorilla/mux \
		coreos:etcd:v3.3.13:coreos_etcd/vendor/github.com/coreos/etcd \
		coreos:go-systemd:d3cd4ed1dbcf:coreos_go_systemd/vendor/github.com/coreos/go-systemd \
		cpu:goacmedns:v0.0.1:cpu_goacmedns/vendor/github.com/cpu/goacmedns \
		davecgh:go-spew:v1.1.1:davecgh_go_spew/vendor/github.com/davecgh/go-spew \
		dgrijalva:jwt-go:v3.2.0:dgrijalva_jwt_go/vendor/github.com/dgrijalva/jwt-go \
		dimchansky:utfbom:v1.1.0:dimchansky_utfbom/vendor/github.com/dimchansky/utfbom \
		dnsimple:dnsimple-go:v0.30.0:dnsimple_dnsimple_go/vendor/github.com/dnsimple/dnsimple-go \
		docker:cli:740919cc7fc0:docker_cli/vendor/github.com/docker/cli \
		docker:distribution:v2.7.1:docker_distribution/vendor/github.com/docker/distribution \
		docker:docker-credential-helpers:v0.6.3:docker_docker_credential_helpers/vendor/github.com/docker/docker-credential-helpers \
		docker:engine:5f6d6f3f2203:docker_engine/vendor/github.com/docker/docker \
		docker:engine:5f6d6f3f2203:docker_engine_1/vendor/github.com/docker/docker \
		docker:go-connections:v0.4.0:docker_go_connections/vendor/github.com/docker/go-connections \
		docker:go-metrics:b84716841b82:docker_go_metrics/vendor/github.com/docker/go-metrics \
		docker:go-units:v0.4.0:docker_go_units/vendor/github.com/docker/go-units \
		docker:libcompose:eac9fe1b8b03:docker_libcompose/vendor/github.com/docker/libcompose \
		docker:libtrust:aabc10ec26b7:docker_libtrust/vendor/github.com/docker/libtrust \
		donovanhide:eventsource:b8f31a59085e:donovanhide_eventsource/vendor/github.com/donovanhide/eventsource \
		eapache:channels:v1.1.0:eapache_channels/vendor/github.com/eapache/channels \
		eapache:queue:v1.1.0:eapache_queue/vendor/github.com/eapache/queue \
		elastic:apm-agent-go:v1.7.0:elastic_apm_agent_go/vendor/go.elastic.co/apm \
		elastic:go-fastjson:v1.0.0:elastic_go_fastjson/vendor/go.elastic.co/fastjson \
		elastic:go-sysinfo:v1.1.1:elastic_go_sysinfo/vendor/github.com/elastic/go-sysinfo \
		elastic:go-windows:v1.0.0:elastic_go_windows/vendor/github.com/elastic/go-windows \
		elazarl:go-bindata-assetfs:v1.0.0:elazarl_go_bindata_assetfs/vendor/github.com/elazarl/go-bindata-assetfs \
		emicklei:go-restful:v2.9.5:emicklei_go_restful/vendor/github.com/emicklei/go-restful \
		etcd-io:etcd:v3.3.13:etcd_io_etcd/vendor/go.etcd.io/etcd \
		evanphx:json-patch:v4.5.0:evanphx_json_patch/vendor/github.com/evanphx/json-patch \
		exoscale:egoscale:v0.18.1:exoscale_egoscale/vendor/github.com/exoscale/egoscale \
		fatih:structs:v1.1.0:fatih_structs/vendor/github.com/fatih/structs \
		felixge:httpsnoop:v1.0.0:felixge_httpsnoop/vendor/github.com/felixge/httpsnoop \
		flynn:go-shlex:3f9db97f8568:flynn_go_shlex/vendor/github.com/flynn/go-shlex \
		fsnotify:fsnotify:v1.4.7:fsnotify_fsnotify/vendor/gopkg.in/fsnotify.v1 \
		gambol99:go-marathon:99a156b96fb2:gambol99_go_marathon/vendor/github.com/gambol99/go-marathon \
		go-acme:lego:v3.5.0:go_acme_lego/vendor/github.com/go-acme/lego/v3 \
		go-errors:errors:v1.0.1:go_errors_errors/vendor/github.com/go-errors/errors \
		go-inf:inf:v0.9.1:go_inf_inf/vendor/gopkg.in/inf.v0 \
		go-ini:ini:v1.51.1:go_ini_ini/vendor/gopkg.in/ini.v1 \
		go-kit:kit:v0.9.0:go_kit_kit/vendor/github.com/go-kit/kit \
		go-logfmt:logfmt:v0.4.0:go_logfmt_logfmt/vendor/github.com/go-logfmt/logfmt \
		go-openapi:jsonpointer:v0.19.3:go_openapi_jsonpointer/vendor/github.com/go-openapi/jsonpointer \
		go-openapi:jsonreference:v0.19.3:go_openapi_jsonreference/vendor/github.com/go-openapi/jsonreference \
		go-openapi:spec:v0.19.3:go_openapi_spec/vendor/github.com/go-openapi/spec \
		go-openapi:swag:v0.19.5:go_openapi_swag/vendor/github.com/go-openapi/swag \
		go-redis:redis:v5.2.9:go_redis_redis/vendor/gopkg.in/redis.v5 \
		go-resty:resty:v1.12.0:go_resty_resty/vendor/gopkg.in/resty.v1 \
		go-yaml:yaml:v2.2.8:go_yaml_yaml/vendor/gopkg.in/yaml.v2 \
		gofrs:uuid:v3.2.0:gofrs_uuid/vendor/github.com/gofrs/uuid \
		gogo:protobuf:v1.3.0:gogo_protobuf/vendor/github.com/gogo/protobuf \
		golang:appengine:v1.6.5:golang_appengine/vendor/google.golang.org/appengine \
		golang:crypto:1b76d66859c6:golang_crypto/vendor/golang.org/x/crypto \
		golang:groupcache:8c9f03a8e57e:golang_groupcache/vendor/github.com/golang/groupcache \
		golang:mod:v0.2.0:golang_mod/vendor/golang.org/x/mod \
		golang:net:244492dfa37a:golang_net/vendor/golang.org/x/net \
		golang:oauth2:bf48bf16ab8d:golang_oauth2/vendor/golang.org/x/oauth2 \
		golang:protobuf:v1.3.4:golang_protobuf/vendor/github.com/golang/protobuf \
		golang:sync:cd5d95a43a6e:golang_sync/vendor/golang.org/x/sync \
		golang:sys:5c8b2ff67527:golang_sys/vendor/golang.org/x/sys \
		golang:text:v0.3.2:golang_text/vendor/golang.org/x/text \
		golang:time:555d28b269f0:golang_time/vendor/golang.org/x/time \
		golang:tools:95d2e580d8eb:golang_tools/vendor/golang.org/x/tools \
		golang:xerrors:9bdfabe68543:golang_xerrors/vendor/golang.org/x/xerrors \
		google:go-cmp:v0.4.0:google_go_cmp/vendor/github.com/google/go-cmp \
		google:go-genproto:506484158171:google_go_genproto/vendor/google.golang.org/genproto \
		google:go-github:v28.1.1:google_go_github/vendor/github.com/google/go-github/v28 \
		google:go-querystring:v1.0.0:google_go_querystring/vendor/github.com/google/go-querystring \
		google:gofuzz:v1.0.0:google_gofuzz/vendor/github.com/google/gofuzz \
		google:uuid:v1.1.1:google_uuid/vendor/github.com/google/uuid \
		googleapis:gax-go:v2.0.5:googleapis_gax_go/vendor/github.com/googleapis/gax-go/v2 \
		googleapis:gnostic:v0.1.0:googleapis_gnostic/vendor/github.com/googleapis/gnostic \
		googleapis:google-api-go-client:v0.20.0:googleapis_google_api_go_client/vendor/google.golang.org/api \
		googleapis:google-cloud-go:v0.54.0:googleapis_google_cloud_go/vendor/cloud.google.com/go \
		gophercloud:gophercloud:v0.3.0:gophercloud_gophercloud/vendor/github.com/gophercloud/gophercloud \
		gorilla:context:v1.1.1:gorilla_context/vendor/github.com/gorilla/context \
		gorilla:websocket:v1.4.2:gorilla_websocket/vendor/github.com/gorilla/websocket \
		gravitational:trace:a535a178675f:gravitational_trace/vendor/github.com/gravitational/trace \
		grpc:grpc-go:v1.27.1:grpc_grpc_go/vendor/google.golang.org/grpc \
		hashicorp:consul:v1.3.0:hashicorp_consul/vendor/github.com/hashicorp/consul/api \
		hashicorp:go-cleanhttp:v0.5.1:hashicorp_go_cleanhttp/vendor/github.com/hashicorp/go-cleanhttp \
		hashicorp:go-immutable-radix:v1.0.0:hashicorp_go_immutable_radix/vendor/github.com/hashicorp/go-immutable-radix \
		hashicorp:go-rootcerts:v1.0.0:hashicorp_go_rootcerts/vendor/github.com/hashicorp/go-rootcerts \
		hashicorp:go-version:v1.2.0:hashicorp_go_version/vendor/github.com/hashicorp/go-version \
		hashicorp:golang-lru:v0.5.1:hashicorp_golang_lru/vendor/github.com/hashicorp/golang-lru \
		hashicorp:serf:v0.8.2:hashicorp_serf/vendor/github.com/hashicorp/serf \
		huandu:xstrings:v1.2.0:huandu_xstrings/vendor/github.com/huandu/xstrings \
		iij:doapi:0bbf12d6d7df:iij_doapi/vendor/github.com/iij/doapi \
		imdario:mergo:v0.3.5:imdario_mergo/vendor/github.com/imdario/mergo \
		influxdata:influxdb1-client:fc22c7df067e:influxdata_influxdb1_client/vendor/github.com/influxdata/influxdb1-client \
		instana:go-sensor:v1.5.1:instana_go_sensor/vendor/github.com/instana/go-sensor \
		jcmturner:goidentity:v3.0.0:jcmturner_goidentity/vendor/gopkg.in/jcmturner/goidentity.v3 \
		jmespath:go-jmespath:c2b33e8439af:jmespath_go_jmespath/vendor/github.com/jmespath/go-jmespath \
		joeshaw:multierror:69b34d4ec901:joeshaw_multierror/vendor/github.com/joeshaw/multierror \
		jonboulle:clockwork:v0.1.0:jonboulle_clockwork/vendor/github.com/jonboulle/clockwork \
		json-iterator:go:v1.1.8:json_iterator_go/vendor/github.com/json-iterator/go \
		kolo:xmlrpc:07c4ee3fd181:kolo_xmlrpc/vendor/github.com/kolo/xmlrpc \
		konsorten:go-windows-terminal-sequences:v1.0.2:konsorten_go_windows_terminal_sequences/vendor/github.com/konsorten/go-windows-terminal-sequences \
		kr:logfmt:b84e30acd515:kr_logfmt/vendor/github.com/kr/logfmt \
		kubernetes-sigs:yaml:v1.1.0:kubernetes_sigs_yaml/vendor/sigs.k8s.io/yaml \
		kubernetes:api:v0.17.3:kubernetes_api/vendor/k8s.io/api \
		kubernetes:apimachinery:v0.17.3:kubernetes_apimachinery/vendor/k8s.io/apimachinery \
		kubernetes:client-go:v0.17.3:kubernetes_client_go/vendor/k8s.io/client-go \
		kubernetes:code-generator:v0.17.3:kubernetes_code_generator/vendor/k8s.io/code-generator \
		kubernetes:gengo:26a664648505:kubernetes_gengo/vendor/k8s.io/gengo \
		kubernetes:klog:v1.0.0:kubernetes_klog/vendor/k8s.io/klog \
		kubernetes:kube-openapi:30be4d16710a:kubernetes_kube_openapi/vendor/k8s.io/kube-openapi \
		kubernetes:utils:e782cd3c129f:kubernetes_utils/vendor/k8s.io/utils \
		labbsr0x:bindman-dns-webhook:v1.0.2:labbsr0x_bindman_dns_webhook/vendor/github.com/labbsr0x/bindman-dns-webhook \
		labbsr0x:goh:v1.0.1:labbsr0x_goh/vendor/github.com/labbsr0x/goh \
		libkermit:compose:c04e39c026ad:libkermit_compose/vendor/github.com/libkermit/compose \
		libkermit:docker-check:1113af38e591:libkermit_docker_check/vendor/github.com/libkermit/docker-check \
		libkermit:docker:e6674d32b807:libkermit_docker/vendor/github.com/libkermit/docker \
		linode:linodego:v0.10.0:linode_linodego/vendor/github.com/linode/linodego \
		liquidweb:liquidweb-go:v1.6.0:liquidweb_liquidweb_go/vendor/github.com/liquidweb/liquidweb-go \
		looplab:fsm:v0.1.0:looplab_fsm/vendor/github.com/looplab/fsm \
		magiconair:properties:v1.8.1:magiconair_properties/vendor/github.com/magiconair/properties \
		mailgun:timetools:7e6055773c51:mailgun_timetools/vendor/github.com/mailgun/timetools \
		mailgun:ttlmap:c1c17f74874f:mailgun_ttlmap/vendor/github.com/mailgun/ttlmap \
		mailru:easyjson:v0.7.0:mailru_easyjson/vendor/github.com/mailru/easyjson \
		matttproud:golang_protobuf_extensions:v1.0.1:matttproud_golang_protobuf_extensions/vendor/github.com/matttproud/golang_protobuf_extensions \
		miekg:dns:v1.1.27:miekg_dns/vendor/github.com/miekg/dns \
		mitchellh:copystructure:v1.0.0:mitchellh_copystructure/vendor/github.com/mitchellh/copystructure \
		mitchellh:go-homedir:v1.1.0:mitchellh_go_homedir/vendor/github.com/mitchellh/go-homedir \
		mitchellh:hashstructure:v1.0.0:mitchellh_hashstructure/vendor/github.com/mitchellh/hashstructure \
		mitchellh:mapstructure:v1.1.2:mitchellh_mapstructure/vendor/github.com/mitchellh/mapstructure \
		mitchellh:reflectwalk:v1.0.0:mitchellh_reflectwalk/vendor/github.com/mitchellh/reflectwalk \
		modern-go:concurrent:bacd9c7ef1dd:modern_go_concurrent/vendor/github.com/modern-go/concurrent \
		modern-go:reflect2:v1.0.1:modern_go_reflect2/vendor/github.com/modern-go/reflect2 \
		morikuni:aec:39771216ff4c:morikuni_aec/vendor/github.com/morikuni/aec \
		namedotcom:go:08470befbe04:namedotcom_go/vendor/github.com/namedotcom/go \
		nrdcg:auroradns:v1.0.1:nrdcg_auroradns/vendor/github.com/nrdcg/auroradns \
		nrdcg:dnspod-go:v0.4.0:nrdcg_dnspod_go/vendor/github.com/nrdcg/dnspod-go \
		nrdcg:goinwx:v0.6.1:nrdcg_goinwx/vendor/github.com/nrdcg/goinwx \
		nrdcg:namesilo:v0.2.1:nrdcg_namesilo/vendor/github.com/nrdcg/namesilo \
		ns1:ns1-go:b51389932cbc:ns1_ns1_go/vendor/gopkg.in/ns1/ns1-go.v2 \
		opencontainers:go-digest:v1.0.0-rc1:opencontainers_go_digest/vendor/github.com/opencontainers/go-digest \
		opencontainers:image-spec:v1.0.1:opencontainers_image_spec/vendor/github.com/opencontainers/image-spec \
		opencontainers:runc:v1.0.0-rc10:opencontainers_runc/vendor/github.com/opencontainers/runc \
		opentracing-contrib:go-observer:a52f23424492:opentracing_contrib_go_observer/vendor/github.com/opentracing-contrib/go-observer \
		opentracing:basictracer-go:v1.0.0:opentracing_basictracer_go/vendor/github.com/opentracing/basictracer-go \
		opentracing:opentracing-go:v1.1.0:opentracing_opentracing_go/vendor/github.com/opentracing/opentracing-go \
		openzipkin-contrib:zipkin-go-opentracing:v0.4.5:openzipkin_contrib_zipkin_go_opentracing/vendor/github.com/openzipkin-contrib/zipkin-go-opentracing \
		openzipkin:zipkin-go:v0.2.2:openzipkin_zipkin_go/vendor/github.com/openzipkin/zipkin-go \
		oracle:oci-go-sdk:v7.0.0:oracle_oci_go_sdk/vendor/github.com/oracle/oci-go-sdk \
		ovh:go-ovh:ba5adb4cf014:ovh_go_ovh/vendor/github.com/ovh/go-ovh \
		patrickmn:go-cache:v2.1.0:patrickmn_go_cache/vendor/github.com/patrickmn/go-cache \
		philhofer:fwd:v1.0.0:philhofer_fwd/vendor/github.com/philhofer/fwd \
		pkg:errors:v0.8.1:pkg_errors/vendor/github.com/pkg/errors \
		pmezard:go-difflib:v1.0.0:pmezard_go_difflib/vendor/github.com/pmezard/go-difflib \
		prometheus:client_golang:v1.1.0:prometheus_client_golang/vendor/github.com/prometheus/client_golang \
		prometheus:client_model:14fe0d1b01d4:prometheus_client_model/vendor/github.com/prometheus/client_model \
		prometheus:common:v0.6.0:prometheus_common/vendor/github.com/prometheus/common \
		prometheus:procfs:v0.0.5:prometheus_procfs/vendor/github.com/prometheus/procfs \
		rancher:go-rancher-metadata:7f4c936a06ac:rancher_go_rancher_metadata/vendor/github.com/rancher/go-rancher-metadata \
		sacloud:libsacloud:v1.26.1:sacloud_libsacloud/vendor/github.com/sacloud/libsacloud \
		samuel:go-zookeeper:c4fab1ac1bec:samuel_go_zookeeper/vendor/github.com/samuel/go-zookeeper \
		santhosh-tekuri:jsonschema:v1.2.4:santhosh_tekuri_jsonschema/vendor/github.com/santhosh-tekuri/jsonschema \
		sirupsen:logrus:v1.4.2:sirupsen_logrus/vendor/github.com/sirupsen/logrus \
		spf13:pflag:v1.0.5:spf13_pflag/vendor/github.com/spf13/pflag \
		square:go-jose:v2.3.1:square_go_jose/vendor/gopkg.in/square/go-jose.v2 \
		stretchr:objx:v0.2.0:stretchr_objx/vendor/github.com/stretchr/objx \
		stretchr:testify:v1.5.1:stretchr_testify/vendor/github.com/stretchr/testify \
		stvp:go-udp-testing:06b61409b154:stvp_go_udp_testing/vendor/github.com/stvp/go-udp-testing \
		timewasted:linode:37e84520dcf7:timewasted_linode/vendor/github.com/timewasted/linode \
		tinylib:msgp:v1.0.2:tinylib_msgp/vendor/github.com/tinylib/msgp \
		transip:gotransip:v5.8.2:transip_gotransip/vendor/github.com/transip/gotransip \
		uber-go:atomic:v1.4.0:uber_go_atomic/vendor/go.uber.org/atomic \
		uber-go:ratelimit:c15da0234277:uber_go_ratelimit/vendor/go.uber.org/ratelimit \
		uber:jaeger-client-go:v2.22.1:uber_jaeger_client_go/vendor/github.com/uber/jaeger-client-go \
		uber:jaeger-lib:v2.2.0:uber_jaeger_lib/vendor/github.com/uber/jaeger-lib \
		unrolled:render:v1.0.2:unrolled_render/vendor/github.com/unrolled/render \
		unrolled:secure:v1.0.7:unrolled_secure/vendor/github.com/unrolled/secure \
		vdemeester:shakers:v0.1.0:vdemeester_shakers/vendor/github.com/vdemeester/shakers \
		vulcand:oxy:v1.1.0:vulcand_oxy/vendor/github.com/vulcand/oxy \
		vulcand:predicate:v1.1.0:vulcand_predicate/vendor/github.com/vulcand/predicate \
		vultr:govultr:v0.1.4:vultr_govultr/vendor/github.com/vultr/govultr \
		xeipuuv:gojsonpointer:4e3ac2762d5f:xeipuuv_gojsonpointer/vendor/github.com/xeipuuv/gojsonpointer \
		xeipuuv:gojsonreference:bd5ef7bd5415:xeipuuv_gojsonreference/vendor/github.com/xeipuuv/gojsonreference \
		xeipuuv:gojsonschema:v1.2.0:xeipuuv_gojsonschema/vendor/github.com/xeipuuv/gojsonschema

PLIST_FILES=	bin/traefik \
		"@sample etc/traefik.toml.sample"

post-patch:
	# Install a sample configuration file which works by default
	# without manual tweaking
	${REINPLACE_CMD} -e 's|:80|:8088|' -e 's|:443|:8443|' \
			 -e 's|\[docker|# \[docker|' ${WRKSRC}/traefik.sample.toml
	cd ${GO_WRKSRC}; ${SETENV} ${MAKE_ENV} ${GO_ENV} ${GO_CMD} generate

post-install:
	${INSTALL_DATA} ${WRKSRC}/traefik.sample.toml ${STAGEDIR}${PREFIX}/etc/traefik.toml.sample

.include <bsd.port.mk>
