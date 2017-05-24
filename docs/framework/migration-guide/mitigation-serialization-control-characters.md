---
title: "Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: be68f399587910e290fc3487b887ca566c2c9f97
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer

Für Apps von .NET Framework 4.7 an hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8. 
 
## <a name="impact"></a>Auswirkungen

In .NET Framework 4.6.2 und früheren Versionen serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den ECMAScript V6 und V8-Standards kompatibel ist.

Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel. Dies betrifft die folgenden APIs:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Problemumgehung

Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.

Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Siehe auch
[Änderungen der Neuzuweisungen in .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

