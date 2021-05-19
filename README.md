# spfx-mgt-multi-webpart
Repro of issue with mgt and multiple webparts. just made these completely seperate to fully test 2 webpart scenario.

# Environment:
* Node: 14.16.1
* npm: 6.14.12
* spfx: 1.12.1
* mgt: preview 43b849f (2021-05-19) from [here](https://github.com/microsoftgraph/microsoft-graph-toolkit/actions/workflows/push.yml?query=branch%3Amain)

# Steps:
1. git clone https://github.com/Greg-Hitchon/spfx-mgt-multi-webpart.git
1. Open mgt-demo-1
1. Run `npm i`
1. Run `gulp clean; gulp bundle --ship; gulp package-solution --ship;`
1. Open mgt-demo-2
1. Run `npm i`
1. Run `gulp clean; gulp bundle --ship; gulp package-solution --ship;`
1. Deploy the `mgt-spfx.sppkg` package to SharePoint
1. Deploy each of the mgt-demo-*.sppkg files to SharePoint 
1. Add mgt-demo-1 to a page by itself - Works
1. Add mgt-demo-2 to a page by itself - Works
1. Add both to a page, first loads, second - `the name "mgt-mock-provider" has already been used with this registry`

