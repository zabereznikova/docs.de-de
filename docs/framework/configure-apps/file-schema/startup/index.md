---
title: Schema für Starteinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "61701514"
---
# <a name="startup-settings-schema"></a>Schema für Starteinstellungen

Starteinstellungen geben die Version der Common Language Runtime an, die die Anwendung ausführen soll.  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Anwendungen, die mit Laufzeitversion 1,1 erstellt wurden, sollten das- **\<supportedRuntime>** Element verwenden|  
|[\<supportedRuntime>](supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|  
|[\<startup>](startup-element.md)|Enthält die **\<requiredRuntime>** **\<supportedRuntime>** Elemente und.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
