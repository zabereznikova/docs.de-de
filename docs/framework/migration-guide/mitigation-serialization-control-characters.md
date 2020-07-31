---
title: Serialisierung von Steuerzeichen mit DataContractJsonSerializer
description: Hier erfahren Sie mehr darüber, wie sich die Serialisierung von Steuerzeichen geändert hat, damit diese mit ECMAScript V6 und V8 in .NET Framework 4.7 konform ist.
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: a317884da014097a7a60aef2cef4ec146ccb04f7
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475384"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Entschärfung: Serialisierung von Steuerzeichen mit DataContractJsonSerializer

Ab .NET Framework 4.7 hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8.

## <a name="impact"></a>Auswirkungen

Bis .NET Framework 4.6.2 serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den Standards ECMAScript V6 und V8 kompatibel ist.

Für Apps mit Zielversionen ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel. Dies betrifft die folgenden APIs:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Minderung

Für Apps mit Zielversionen ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.

Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
