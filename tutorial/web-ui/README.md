---
description: Open http://localhost:8080 in your browser. If you build with make all.
---

# Web UI

{% hint style="info" %}
When you build openfild using `make all` the Web UI app is also part of the process.&#x20;

You can skip this section. Following steps are to be used only in case you are building binary and react app separately.
{% endhint %}

### Build the Vue frontend

```
make vue
```

Or

```
cd webui
npm install
npm run build:prod
```

### Run Web UI

```
npm run dev
```

