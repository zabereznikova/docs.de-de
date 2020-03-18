---
title: 'Entschärfung: XML-Schema-Validierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 99cc1eae08697909d89e5c1e46cd604c7da543bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457739"
---
# <a name="mitigation-xml-schema-validation"></a>Entschärfung: XML-Schema-Validierung
In .NET Framework 4.6 erkennt die XSD-Schemavalidierung Verstöße gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.  
  
## <a name="impact"></a>Auswirkungen  
 Die Auswirkung dieser Änderung sollte minimal sein: In Abhängigkeit der Schemaspezifikation wir ein Schemavalidierungsfehler erwartet, wenn `xsd:unique` mithilfe eines Verbundschlüssels mit einem leeren Schlüssel verletzt wird.  
  
## <a name="mitigation"></a>Minderung  
 Ob ein Schemavalidierungsfehler erkannt wird, wenn ein Verbundschlüssel über einen leeren Schlüssel verfügt, kann konfiguriert werden:  
  
- Bei Apps, die auf .NET Framework 4.6 ausgerichtet sind, ist die Erkennung des Schemavalidierungsfehlers standardmäßig aktiviert. Es ist jedoch möglich, dieses Verhalten zu deaktivieren, sodass der Schemavalidierungsfehler nicht erkannt wird.  
  
- In Apps, die unter .NET Framework 4.6 ausgeführt werden, aber auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, wird standardmäßig kein Schemavalidierungsfehler erkannt. Es ist jedoch möglich, dieses Verhalten zu aktivieren, sodass der Schemavalidierungsfehler erkannt wird.  
  
 Dieses Verhalten kann mithilfe der Klasse <xref:System.AppContext> konfiguriert werden, um den Wert des Switches `System.Xml.IgnoreEmptyKeySequences` zu definieren. Da der Standardwert des Switches `false` (leere Schlüsselsequenzen werden nicht ignoriert) lautet, können auf .NET Framework 4.6 ausgerichtete Apps dieses Verhalten deaktivieren, indem der Wert des Switches mithilfe des folgenden Codes auf `true` festgelegt wird:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Da der Standardwert des Switches bei Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, `true` (leere Schlüsselsequenzen werden ignoriert) lautet, kann sichergestellt werden, dass ein Verbundschlüssel mit einem leeren Schlüssel einen Schemavalidierungsfehler generiert, indem der Wert des Switches mithilfe des folgenden Codes auf `false` festgelegt wird.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Anwendungskompatibilität](application-compatibility.md)
