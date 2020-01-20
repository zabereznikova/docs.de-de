---
title: Serialisierung von Steuerzeichen mit DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: 209f7827e61ef72de1d64fad46dc9f241fa6edef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346574"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="ddef4-102">Entschärfung: Serialisierung von Steuerzeichen mit DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="ddef4-102">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="ddef4-103">Für Apps von .NET Framework 4.7 an hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8.</span><span class="sxs-lookup"><span data-stu-id="ddef4-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="ddef4-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="ddef4-104">Impact</span></span>

<span data-ttu-id="ddef4-105">In .NET Framework 4.6.2 und früheren Versionen serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den ECMAScript V6- und V8-Standards kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ddef4-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="ddef4-106">Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel.</span><span class="sxs-lookup"><span data-stu-id="ddef4-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="ddef4-107">Dies betrifft die folgenden APIs:</span><span class="sxs-lookup"><span data-stu-id="ddef4-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a><span data-ttu-id="ddef4-108">Minderung</span><span class="sxs-lookup"><span data-stu-id="ddef4-108">Mitigation</span></span>

<span data-ttu-id="ddef4-109">Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ddef4-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="ddef4-110">Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ddef4-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="ddef4-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddef4-111">See also</span></span>

- [<span data-ttu-id="ddef4-112">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="ddef4-112">Application compatibility</span></span>](application-compatibility.md)
