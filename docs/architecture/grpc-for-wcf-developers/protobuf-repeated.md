---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie protobuf Sammlungen behandelt und wie Sie mit .NET-Auflistungen in Beziehung stehen.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542958"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Wiederholte Felder für Listen und Arrays

Listen werden im Protokollpuffer (protobuf) mithilfe des `repeated` Prefix-Schlüssel Worts angegeben. Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Im generierten Code werden `repeated` Felder durch den `Google.Protobuf.Collections.RepeatedField<T>` generischen Typ und nicht durch einen der integrierten .net-Auflistungs Typen dargestellt. 

Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist. Es implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, z. b. <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IEnumerable%601>. Sie können LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren.

>[!div class="step-by-step"]
>[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)
