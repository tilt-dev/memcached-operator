k8s_yaml(['deploy/operator.yaml', 'deploy/role_binding.yaml', 'deploy/role.yaml', 'deploy/service_account.yaml'])
k8s_yaml('deploy/crds/cache.example.com_memcacheds_crd.yaml')
k8s_yaml('deploy/crds/cache.example.com_v1alpha1_memcached_cr.yaml')

custom_build(
  'gcr.io/windmill-public-containers/memcached-operator',
  'operator-sdk build $EXPECTED_REF',
  ['cmd/manager', 'pkg', 'go.mod', 'go.sum', 'version', 'tools.go'],
)

local_resource('Regenerate CRD', 'operator-sdk generate k8s', deps='deploy/crds/cache.example.com_memcacheds_crd.yaml')
