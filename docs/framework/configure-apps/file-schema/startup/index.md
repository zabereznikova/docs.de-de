---
title: Schema für Starteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68f37e3efca784b94be90d5779c9bc402f144448
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465472"
---
# <a name="startup-settings-schema"></a>Schema für Starteinstellungen
Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Anwendungen, die mit Version 1.1 der Runtime erstellt wurden, sollten das **\<supportedRuntime>**-Element verwenden.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
|[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|Enthält die Elemente **\<requiredRuntime>** und **\<supportedRuntime>**.|  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
