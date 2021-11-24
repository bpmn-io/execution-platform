# @bpmn-io/execution-platform

[![CI](https://github.com/bpmn-io/execution-platform/workflows/CI/badge.svg)](https://github.com/bpmn-io/execution-platform/actions?query=workflow%3ACI)

Set `executionPlatform` and `executionPlatformVersion` in your BPMN and DMN diagrams.

## Usage

```javascript
import BpmnModeler from 'bpmn-js/lib/Modeler';

import ExecutionPlatformModule from '@bpmn-io/execution-platform';


// extend the BPMN editor with the exporter module
var modeler = new BpmnModeler({
  additionalModules: [
    ExecutionPlatformModule
  ]
});

var executionPlatformHelper = modeler.get('executionPlatform');

executionPlatformHelper.setExecutionPlatform({ name: 'Camunda Cloud', version: '1.3.0' });

var executionPlatform = executionPlatformHelper.getExecutionPlatform();

// { name: 'Camunda Cloud', version: '1.3.0' }
console.log(executionPlatform);

// see the meta-data appear on save
modeler.saveXML(function(err, xml) {

  xml; // ... <bpmn:Definitions ... modeler:executionPlatform="Camunda Cloud" modeler:executionPlatformVersion="1.3.0">...
});
```

## License

MIT
