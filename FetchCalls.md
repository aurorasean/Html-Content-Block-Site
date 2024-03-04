---
title: Example Fetch calls
layout: home
---

## Example call

```
const tablePageContentId = "7831683"
const data = await window.fetchConfluence(tablePageContentId)
body = data.body.export_view.value; 

// returns html content that the page would of rendered
```

## The Type interface for the method

```
interface ConfluenceExportView {
    body: {
        export_view: {
            value: string;
        }
    }
}
declare global {
    interface Window {
        // takes an input of a confluence Content Id, and returns the export_view content 
        fetchConfluence: (id: string) => Promise<ConfluenceExportView>;
    }
}
```