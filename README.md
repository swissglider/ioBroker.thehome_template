![Logo](admin/thehome_template.png)

# ioBroker.thehome_template

[![NPM version](https://img.shields.io/npm/v/iobroker.thehome_template.svg)](https://www.npmjs.com/package/iobroker.thehome_template)
[![Downloads](https://img.shields.io/npm/dm/iobroker.thehome_template.svg)](https://www.npmjs.com/package/iobroker.thehome_template)
![Number of Installations](https://iobroker.live/badges/thehome_template-installed.svg)
![Current version in stable repository](https://iobroker.live/badges/thehome_template-stable.svg)
[![Dependency Status](https://img.shields.io/david/swissglider/iobroker.thehome_template.svg)](https://david-dm.org/swissglider/iobroker.thehome_template)

[![NPM](https://nodei.co/npm/iobroker.thehome_template.png?downloads=true)](https://nodei.co/npm/iobroker.thehome_template/)

**Tests:** ![Test and Release](https://github.com/swissglider/ioBroker.thehome_template/workflows/Test%20and%20Release/badge.svg)

## thehome_template adapter for ioBroker

This is the Home Template for all the adapters from Swissglider

## Instalation Steps

1.  > `npx @iobroker/create-adapter`

       <details>
       <summary>Details</summary>

    ```javascript
        {
            "cli": true,
            "target": "directory",
            "adapterName": "thehome_template",
            "title": "The Home Template",
            "description": "This is the Home Template for all the adapters from Swissglider",
            "keywords": ["template", "theHome", "Swissglider", "test", "not productive"],
            "expert": "yes",
            "features": ["adapter"],
            "adminFeatures": [],
            "type": "general",
            "startMode": "daemon",
            "connectionType": "local",
            "dataSource": "push",
            "connectionIndicator": "no",
            "language": "TypeScript",
            "adminReact": "no",
            "tabReact": "no",
            "tools": ["ESLint", "Prettier"],
            "releaseScript": "yes",
            "devServer": "yes",
            "devServerPort": 8066,
            "indentation": "Space (4)",
            "quotes": "single",
            "es6class": "yes",
            "authorName": "Swissglider",
            "authorGithub": "swissglider",
            "authorEmail": "npm@mailschweiz.com",
            "gitRemoteProtocol": "HTTPS",
            "gitCommit": "yes",
            "defaultBranch": "main",
            "license": "MIT License",
            "dependabot": "no",
            "creatorVersion": "2.0.2"
        }
    ```

    </details>

2.  create `jsonConfig.json` to admin and add:
    <details>
    <summary>Details</summary>

    ```javascript
    {
        "i18n": true,
        "type": "tabs",
        "items": {
            "_general": {
                "type": "panel",
                "label": "General settings",
                "items": {
                    "protocol": {
                        "type": "select",
                        "options": [
                            {
                                "label": {
                                    "en": "CoAP and HTTP",
                                    "de": "CoAP und HTTP",
                                    "ru": "CoAP и HTTP",
                                    "pt": "CoAP e HTTP",
                                    "nl": "CoAP en HTTP",
                                    "fr": "CoAP et HTTP",
                                    "it": "CoAP e HTTP",
                                    "es": "CoAP y HTTP",
                                    "pl": "CoAP i HTTP",
                                    "zh-cn": "CoAP 和 HTTP"
                                },
                                "value": "coap"
                            },
                            {
                                "label": {
                                    "en": "MQTT and HTTP",
                                    "de": "MQTT und HTTP",
                                    "ru": "MQTT и HTTP",
                                    "pt": "MQTT e HTTP",
                                    "nl": "MQTT en HTTP",
                                    "fr": "MQTT et HTTP",
                                    "it": "MQTT e HTTP",
                                    "es": "MQTT y HTTP",
                                    "pl": "MQTT i HTTP",
                                    "zh-cn": "MQTT 和 HTTP"
                                },
                                "value": "mqtt"
                            }
                        ],
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "Shelly protocol"
                    },
                    "httpusername": {
                        "newLine": true,
                        "type": "text",
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "HTTP Username"
                    },
                    "httppassword": {
                        "type": "password",
                        "repeat": false,
                        "visible": true,
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "HTTP Password"
                    },
                    "polltime": {
                        "newLine": true,
                        "type": "number",
                        "min": 5,
                        "max": 86400,
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "Poll time in seconds"
                    },
                    "autoupdate": {
                        "newLine": true,
                        "type": "checkbox",
                        "sm": 12,
                        "md": 12,
                        "lg": 12,
                        "label": "Auto update of new firmware"
                    },
                    "updateUnchangedObjects": {
                        "newLine": true,
                        "type": "checkbox",
                        "sm": 12,
                        "md": 12,
                        "lg": 12,
                        "label": "Update objects even if there is no value change"
                    }
                }
            },
            "_mqtt": {
                "type": "panel",
                "label": "MQTT settings",
                "items": {
                    "bind": {
                        "newLine": true,
                        "type": "ip",
                        "listenOnAllPorts": true,
                        "sm": 12,
                        "md": 8,
                        "lg": 6,
                        "label": "MQTT Listen IP"
                    },
                    "port": {
                        "type": "number",
                        "min": 1,
                        "max": 65535,
                        "sm": 12,
                        "md": 4,
                        "lg": 1,
                        "label": "Port"
                    },
                    "mqttusername": {
                        "newLine": true,
                        "type": "text",
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "MQTT Username"
                    },
                    "mqttpassword": {
                        "type": "password",
                        "repeat": false,
                        "visible": true,
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "MQTT Password"
                    },
                    "qos": {
                        "newLine": true,
                        "type": "select",
                        "options": [
                            {
                                "label": {
                                    "en": "0 - At most once",
                                    "de": "0 - Höchstens einmal",
                                    "ru": "0 - Не более одного раза",
                                    "pt": "0 - no máximo uma vez",
                                    "nl": "0 - Maximaal één keer",
                                    "fr": "0 - Au plus une fois",
                                    "it": "0 - Al massimo una volta",
                                    "es": "0: como máximo una vez",
                                    "pl": "0 - Co najwyżej raz",
                                    "zh-cn": "0 - 最多一次"
                                },
                                "value": 0
                            },
                            {
                                "label": {
                                    "en": "1 - At least once",
                                    "de": "1 - Mindestens einmal",
                                    "ru": "1 - Хотя бы один раз",
                                    "pt": "1 - pelo menos uma vez",
                                    "nl": "1 - Minstens één keer",
                                    "fr": "1 - Au moins une fois",
                                    "it": "1 - Almeno una volta",
                                    "es": "1 - Al menos una vez",
                                    "pl": "1 - Przynajmniej raz",
                                    "zh-cn": "1 - 至少一次"
                                },
                                "value": 1
                            },
                            {
                                "label": {
                                    "en": "2 - Exactly once",
                                    "de": "2 - Genau einmal",
                                    "ru": "2 - Ровно один раз",
                                    "pt": "2 - Exatamente uma vez",
                                    "nl": "2 - Precies één keer",
                                    "fr": "2 - Exactement une fois",
                                    "it": "2 - Esattamente una volta",
                                    "es": "2 - Exactamente una vez",
                                    "pl": "2 - Dokładnie raz",
                                    "zh-cn": "2 - 恰好一次"
                                },
                                "value": 2
                            }
                        ],
                        "sm": 12,
                        "md": 6,
                        "lg": 6,
                        "label": "Default QoS"
                    }
                }
            },
            "_coap": {
                "type": "panel",
                "label": "CoAP settings",
                "items": {
                    "coapbind": {
                        "newLine": true,
                        "type": "ip",
                        "listenOnAllPorts": true,
                        "sm": 12,
                        "md": 8,
                        "lg": 6,
                        "label": "COAP listen IP"
                    },
                    "blacklist": {
                        "type": "table",
                        "sm": 12,
                        "md": 12,
                        "lg": 12,
                        "label": "Blacklist",
                        "items": [
                            {
                                "type": "text",
                                "attr": "id",
                                "width": "100%",
                                "title": "Device Id",
                                "filter": true,
                                "sort": true,
                                "default": ""
                            }
                        ]
                    }
                }
            }
        }
    }
    ```

     </details>

3.  replace (and adapt) the following part to `io-package.json`:
    <details>
    <summary>Details</summary>

    ```javascript
    "localLink": "%web_protocol%://%ip%:%web_port%/thehome_template/index.html",
        "welcomeScreen": [
            {
                "link": "theHome_template/index.html",
                "name": "theHome_template",
                "img": "theHome_template/img/device-availability.png",
                "color": "#ffe9c8",
                "order": 0
            }
        ],
        "messagebox": true,
        "adminUI": {
            "config": "json"
        },
        "globalDependencies": [
            {
                "admin": ">=5.1.25",
                "web": ">=3.4.16"
            }
        ],
        "dependencies": [
            {
                "js-controller": ">=3.3.0"
            }
        ]
    ```

     </details>

4.  add the `.vscode/settings.json` file
    <details>
    <summary>Details</summary>

    ```javascript
    "[typescriptreact]": {
        // "editor.defaultFormatter": "vscode.typescript-language-features"
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[json]": {
        // "editor.defaultFormatter": "vscode.json-language-features"
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "prettier.semi": true,
    "prettier.useTabs": true,
    "prettier.trailingComma": "all",
    "prettier.tabWidth": 4,
    "prettier.printWidth": 120,
    "prettier.singleQuote": true,
    "prettier.endOfLine": "lf"
    ```

     </details>

5.  Add the `.gitignore` file:
    <details>
    <summary>Details</summary>

    ```
    # added from template
    .git
    .idea

    # ioBroker dev-server
    .dev-server/

    admin/build
    www/*
    !www/t.t
    build


    #reactClientApp

    # dependencies
    reactClientApp/thehome/node_modules
    reactClientApp/thehome/.pnp
    reactClientApp/thehome/.pnp.js

    # testing
    reactClientApp/thehome/coverage

    # production
    reactClientApp/thehome/build

    # misc
    reactClientApp/thehome/.DS_Store
    reactClientApp/thehome/.env.local
    reactClientApp/thehome/.env.development.local
    reactClientApp/thehome/.env.test.local
    reactClientApp/thehome/.env.production.local

    reactClientApp/thehome/npm-debug.log*
    reactClientApp/thehome/yarn-debug.log*
    reactClientApp/thehome/yarn-error.log*
    reactClientApp/thehome/.gitignore
    reactClientApp/thehome/README.md
    ```

    </details>

6.  Add the following on `package.json` ro scripts:
    <details>
    <summary>Details</summary>

    ```javascript
    "build:startWebApp": "mkdir -p ./www && rm -rf ./reactClientApp/thehome/build &&  npm --prefix ./reactClientApp/thehome run build && cp -R ./reactClientApp/thehome/build/* ./www/",
    "build:startWebApp_github_actions": "npm --prefix ./reactClientApp/thehome run build && cp -R ./reactClientApp/thehome/build/* ./www/",

    "build": "npm run build:ts && npm run build:startWebApp",
    "build_github_actions": "npm run build:ts && npm run build:startWebApp_github_actions",

    "startWebApp": "cd ./reactClientApp/thehome && npm start"
    ```

    </details>

7.  Add the following to `devDependencies` in the `package.json` file:
    <details>
    <summary>Details</summary>

    ```bash
        "@testing-library/jest-dom": "^5.16.1",
        "@testing-library/react": "^11.2.7",
        "@testing-library/user-event": "^12.8.3",
        "@types/jest": "^26.0.24",
        "@types/react": "^16.14.21",
        "@types/react-dom": "^16.9.14",
        "react": "^17.0.2",
        "react-dom": "^17.0.2",
        "react-scripts": "5.0.0",
        "typescript": "^4.5.4",
        "web-vitals": "^0.2.4",
        "workbox-background-sync": "^5.1.4",
        "workbox-broadcast-update": "^5.1.4",
        "workbox-cacheable-response": "^5.1.4",
        "workbox-core": "^5.1.4",
        "workbox-expiration": "^5.1.4",
        "workbox-google-analytics": "^5.1.4",
        "workbox-navigation-preload": "^5.1.4",
        "workbox-precaching": "^5.1.4",
        "workbox-range-requests": "^5.1.4",
        "workbox-routing": "^5.1.4",
        "workbox-strategies": "^5.1.4",
        "workbox-streams": "^5.1.4"
    ```

    </details>

8.  Create WebApp:
    <details>
    <summary>Details</summary>

    ```bash
    npm install react-scripts@latest && mkdir reactClientApp && cd reactClientApp && npx create-react-app thehome --template cra-template-pwa-typescript && cd .. && mkdir -p ./www && touch ./www/t.t
    ```

    </details>

9.  add the the following line to the `./reactClientApp/thehome/package.json` file:
    <details>
    <summary>Details</summary>

    ```javascript
    "homepage": "./",
    ```

    </details>

10. Add the following after `build:true` in the `.github/workflows/test-and-release.yml` file - 2 times
    <details>
    <summary>Details</summary>

    ```bash
    build-command: 'npm run build_github_actions'
    ```

    </details>

11. Uncomment the deploy part on `.github/workflows/test-and-release.yml`
12. Create the github repository:
    <details>
    <summary>Details</summary>

    ```bash
    # Stage and commit all the files in your project
    git add . && git commit -m "initial commit"

    # if not don install github cli --> https://github.com/cli/cli#installation
    # brew install gh
    gh repo create
    ```

    </details>

13. add the `NPM_TOKEN` to the github repository secrets
14. add the `AUTO_MERGE_TOKEN` with `public_repo` permission on https://github.com/settings/tokens
15. `npm run release prerelease` to create the first release
16. --> after start first you need to install the web adapter !

## Commands

| Script name                 | Description                                       | Link                                                |
| --------------------------- | ------------------------------------------------- | --------------------------------------------------- |
| `npm run startWebApp`       | Only start the web app in reactClientApp/thehome. |                                                     |
| `dev-server upload default` | Compiles and upload to the default server.        | https://github.com/ioBroker/dev-server#command-line |
| `dev-server run default`    | Runs the default server.                          | https://github.com/ioBroker/dev-server#command-line |

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->

### 0.0.2-1 (2022-01-21)

-   (Swissglider) initial release

## License

MIT License

Copyright (c) 2022 Swissglider <npm@mailschweiz.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
