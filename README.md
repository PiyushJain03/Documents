# clouds.yml file used for HDP 2.0 deployment on 3rd March 2016

clouds:
  mycloud:
    codn_username: piyush.jain@hp.com
    codn_password: hp1201tu
    region_name: region1
    cacert: /home/stack/helion/my_cloud/config/tls/certs/galway-public-cert
    insecure: True
    auth:
      auth_url: https://172.16.244.13:5000/v2.0
      project_name: admin
      username: admin
      password: hsykA3rzH
    database:
      trove_enable_ssl: False
      ephemeral_ca_cert: /home/stack/helion/my_cloud/config/tls/certs/galway-public-cert
      external_network: 4e0de08a-4b4d-46d4-aae4-0b15680d903b
      provider_network: 3741da4e-63b1-40e1-b815-2291e8df9371
      ntp_server: 172.16.1.5
      keypair: hlm-keys
      enable_ha: False
      flavor: m1.medium
      database_flavor: m1.medium
      messaging_flavor: m1.medium
      database_volume_size: 10
      logstash_rabbitmq_host: 172.16.240.28
      logstash_rabbitmq_password: DB4lU83d8c1
      hotpools_enabled: True
      hotpools_max_instances: 1
      hotpools_image_name: percona
      hotpools_flavor_names: 'm1.medium'
      project_id: 62c08a0d5f6543179f3b93d9289d01a8
      control_plane_database_volume_type: ceph-backend
      guest_instance_volume_type: ceph-backend
      disable_rollback: true
    helionce:
      deployer_key: helionce-shared
      deployer_flavor: 3
      deployer_ntp_servers: ntpservers
      deployer_dns_servers: dnsservers
      deployer_cloud: 'mycloud'
      username: helionce
    messaging:
      deployer_cloud: msgaas
      deployer_ntp_servers: 172.16.1.5
      deployer_dns_servers: 172.16.1.5
      deployer_flavor: 3
      ##### These settings are optional. If you are not providing a value for them, delete these lines entirely. Do not leave blank.
      #deployer_key: hlm-keys
      deployer_name: msgaas_deployer_01
      deployer_ext_net_id: ext-net
      deployer_cname: msgaas
      #####
  msgaas:
    region_name: region1
    insecure: True
    auth:
      auth_url: http://172.16.240.28:35357/v3
      project_name: msgaas
      username: msgaas
      password: abc123456
      project_domain_name: default
      user_domain_name: default
