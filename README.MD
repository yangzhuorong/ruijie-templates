# 说明
ruijie-templates是基于textFSM规则开发，用于适配ntc-templates的模板库。
该模板库主要适配锐捷DCN产品，并在以下产品和软件版本中经过测试：
1. 6500系列：11.0(5)B9P43S1
2. 6900系列：12.4(1)B0201
3. 18X系列：11.3(1)B6P38S1、11.3(1)B6P41

# 测试说明
该模板库经过内部测试，相关测试用例请查看`/tests/ruijie_os/`目录。

# 安装方法
>前置条件：安装textFSM库和ntc-templates库
方法一：将ruijie-templates并入ntc-templates模板库（推荐）
方法二：独立使用ruijie-templates库，需要设置环境变量，相对复杂（不推荐）

推荐使用方法一将本模板库合并入ntc-templates模块使用，具体操作步骤如下：
#### 下载模板库
```shell
 git clone git@github.com:kevinkrabi/ruijie-templates.git
```
#### 模板文件导入ntc-templates
将templates目录下的所有textfsm文件导入ntc-templates库的templates目录。
以macOS为例：
```shell
cp *.textfsm Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/ntc_templates/templates/
```

#### 添加index信息
以macOS为例，index文件所在路径为：`Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/ntc_templates/templates/index`
找到index文件后用文本编辑软件打开，将以下内容全部复制粘贴到原始文件末尾即可。
>注意：由于ntc-templates模板库匹配原则，为避免异常情况，以下index条目不建议调整顺序！
```
ruijie_os_show_ip_bgp_neighbors_advertised-routes.textfsm, .*, ruijie_os, sh[[ow]] ip bgp nei[[ghbors]](\s+\d+\.\d+\.\d+\.\d+)? adv[[ertised-routes]]
ruijie_os_show_interfaces_transceiver_diagnosis.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] trans[[ceiver]] dia[[gnosis]]
ruijie_os_show_interfaces_status_err-disabled.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] st[[atus]] err[[-disabled]]
ruijie_os_show_interfaces_counters_rate.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] c[[ounters]] r[[ate]](\s+[[up]])?
ruijie_os_show_interfaces_description.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] de[[scription]]
ruijie_os_show_interfaces_transceiver.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] trans[[ceiver]]
ruijie_os_show_lldp_neighbors_detail.textfsm, .*, ruijie_os, sh[[ow]] lld[[p]] neig[[hbors]] de[[tail]]
ruijie_os_show_aggregatePort_summary.textfsm, .*, ruijie_os, sh[[ow]] ag[[gregatePort]] su[[mmary]]
ruijie_os_show_interfaces_switchport.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] sw[[itchport]]
ruijie_os_show_ipv6_interface_brief.textfsm, .*, ruijie_os, sh[[ow]] ipv[[6]] interf[[ace]] b[[rief]]
ruijie_os_show_ip_interface_brief.textfsm, .*, ruijie_os, sh[[ow]] ip int[[erface]] br[[ief]]
ruijie_os_show_ip_community-list.textfsm, .*, ruijie_os, sh[[ow]] ip comm[[unity-list]]
ruijie_os_show_mac-address-table.textfsm, .*, ruijie_os, sh[[ow]] mac[[-address-table]]
ruijie_os_show_interfaces_status.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]] st[[atus]]
ruijie_os_show_upgrade_auto-sync.textfsm, .*, ruijie_os, sh[[ow]] up[[grade]] au[[to-sync]]
ruijie_os_show_ip_bgp_neighbors.textfsm, .*, ruijie_os, sh[[ow]] ip bgp nei[[ghbors]]
ruijie_os_show_ip_route_summary.textfsm, .*, ruijie_os, sh[[ow]] ip ro[[ute]] sum[[mary]]
ruijie_os_show_upgrade_history.textfsm, .*, ruijie_os, sh[[ow]] up[[grade]] his[[ory]]
ruijie_os_show_bgp_all_summary.textfsm, .*, ruijie_os, sh[[ow]] bgp all sum[[mary]]
ruijie_os_show_lldp_neighbors.textfsm, .*, ruijie_os, sh[[ow]] lld[[p]] neig[[hbors]]
ruijie_os_show_ip_prefix-list.textfsm, .*, ruijie_os, sh[[ow]] ip pre[[fix-list]]
ruijie_os_show_ip_bgp_summary.textfsm, .*, ruijie_os, sh[[ow]] ip bgp sum[[mary]]
ruijie_os_show_isis_neighbors.textfsm, .*, ruijie_os, sh[[ow]] isis ne[[ighbors]]
ruijie_os_show_upgrade_status.textfsm, .*, ruijie_os, sh[[ow]] up[[grade]] st[[atus]]
ruijie_os_show_ipv6_neighbors.textfsm, .*, ruijie_os, sh[[ow]] ipv[[6]] ne[[ighbors]]
ruijie_os_show_version_slots.textfsm, .*, ruijie_os, sh[[ow]] ver[[sion]] s[[lots]]
ruijie_os_show_bfd_neighbor.textfsm, .*, ruijie_os, sh[[ow]] bfd ne[[ighbor]]
ruijie_os_show_lacp_summary.textfsm, .*, ruijie_os, sh[[ow]] la[[cp]] su[[mmary]]
ruijie_os_show_arp_detail.textfsm, .*, ruijie_os, sh[[ow]] a[[rp]] d[[etail]]
ruijie_os_show_fan_detail.textfsm, .*, ruijie_os, sh[[ow]] fa[[n]] de[[tail]]
ruijie_os_show_interfaces.textfsm, .*, ruijie_os, sh[[ow]] int[[erfaces]]
ruijie_os_show_route-map.textfsm, .*, ruijie_os, sh[[ow]] route-m[[ap]]
ruijie_os_show_ip_route.textfsm, .*, ruijie_os, sh[[ow]] ip r[[oute]]
ruijie_os_show_manuinfo.textfsm, .*, ruijie_os, sh[[ow]] man[[uinfo]]
ruijie_os_show_logging.textfsm, .*, ruijie_os, sh[[ow]] log[[ging]]
ruijie_os_show_version.textfsm, .*, ruijie_os, sh[[ow]] ver[[sion]]
ruijie_os_show_ip_bgp.textfsm, .*, ruijie_os, sh[[ow]] i[[p]] bgp
ruijie_os_show_clock.textfsm, .*, ruijie_os, sh[[ow]] clo[[ck]]
ruijie_os_show_alarm.textfsm, .*, ruijie_os, sh[[ow]] ala[[rm]]
ruijie_os_show_power.textfsm, .*, ruijie_os, sh[[ow]] pow[[er]]
ruijie_os_show_dldp.textfsm, .*, ruijie_os, sh[[ow]] dl[[dp]]
ruijie_os_show_vlan.textfsm, .*, ruijie_os, sh[[ow]] vlan
ruijie_os_show_vrrp.textfsm, .*, ruijie_os, sh[[ow]] vr[[rp]]
ruijie_os_show_arp.textfsm, .*, ruijie_os, sh[[ow]] a[[rp]]
ruijie_os_show_fan.textfsm, .*, ruijie_os, sh[[ow]] fa[[n]]
ruijie_os_show_vrf.textfsm, .*, ruijie_os, sh[[ow]] vrf
ruijie_os_dir.textfsm, .*, ruijie_os, dir
```

# 参考资料
textFSM：
> https://github.com/google/textfsm

ntc-templates：
> https://github.com/networktocode/ntc-templates

# 联系方式
该模板库是本人利用业余时间自行开发，如遇到异常请多包涵，您在使用过程中发现任何问题都可以与我交流：wupeizhang@ruijie.com.cn