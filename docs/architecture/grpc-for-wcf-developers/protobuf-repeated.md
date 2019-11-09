---
title: 'Wiederholte Felder für Listen und Arrays: GrpC für WCF-Entwickler'
description: Erfahren Sie, wie Sammlungen von protobuf behandelt werden und wie Sie mit .NET-Auflistungen in Beziehung stehen.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841396"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Wiederholte Felder für Listen und Arrays

Listen werden in protobuf mithilfe des `repeated` Prefix-Schlüssel Worts angegeben. Im folgenden Beispiel wird gezeigt, wie eine Liste erstellt wird:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

Im generierten Code werden `repeated` Felder durch den `Google.Protobuf.Collections.RepeatedField<T>` generischen Typ und nicht durch einen der integrierten .net-Auflistungs Typen dargestellt. Der `RepeatedField<T>` Typ enthält den Code, der zum Serialisieren und Deserialisieren der Liste in das binäre Wire-Format erforderlich ist. Es implementiert alle standardmäßigen .net-Auflistungs Schnittstellen, wie z. b. <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IEnumerable%601>, sodass Sie LINQ-Abfragen verwenden oder Sie problemlos in ein Array oder eine Liste konvertieren können.

>[!div class="step-by-step"]
>[Zurück](protobuf-nested-types.md)
>[Weiter](protobuf-reserved.md)
