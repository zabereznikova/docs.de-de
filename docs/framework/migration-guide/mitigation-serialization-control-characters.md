---
title: 'Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer'
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: faa7a32766a3ea1ef9cddcdb8af8fd0dd5a6f287
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457807"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer

Für Apps von .NET Framework 4.7 an hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8. 
 
## <a name="impact"></a>Auswirkungen

In .NET Framework 4.6.2 und früheren Versionen serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den ECMAScript V6- und V8-Standards kompatibel ist.

Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel. Dies betrifft die folgenden APIs:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a>Minderung

Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.

Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
