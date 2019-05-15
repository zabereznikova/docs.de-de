---
title: 'Entschärfung: XML-Schemavalidierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc0232e0187c795fe20e6a99d4a710ba6244e34e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599675"
---
# <a name="mitigation-xml-schema-validation"></a>Entschärfung: XML-Schemavalidierung
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ermittelt die XSD-Schemavalidierung einen Verstoß gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.  
  
## <a name="impact"></a>Auswirkungen  
 Die Auswirkung dieser Änderung sollte minimal sein: In Abhängigkeit der Schemaspezifikation wir ein Schemavalidierungsfehler erwartet, wenn `xsd:unique` mithilfe eines Verbundschlüssels mit einem leeren Schlüssel verletzt wird.  
  
## <a name="mitigation"></a>Minderung  
 Ob ein Schemavalidierungsfehler erkannt wird, wenn ein Verbundschlüssel über einen leeren Schlüssel verfügt, kann konfiguriert werden:  
  
- Angefangen bei den Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen, ist die Ermittlung des Schemavalidierungsfehlers standardmäßig aktiviert. Es ist jedoch möglich, dieses Verhalten abzuwählen, wodurch der Schemavalidierungsfehler nicht ermittelt wird.  
  
- In unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführten Apps, die jedoch auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, wird eine Schemavalidierungsfehler nicht standardmäßig ermittelt. Es ist jedoch möglich, dieses Verhalten zu aktivieren, sodass der Schemavalidierungsfehler ermittelt wird.  
  
 Dieses Verhalten kann mithilfe der Klasse <xref:System.AppContext> konfiguriert werden, um den Wert des Switches `System.Xml.IgnoreEmptyKeySequences` zu definieren. Da der Standardwert des Switches `false` (leere Schlüsselsequenzen werden nicht ignoriert) lautet, können auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielende Apps dieses Verhalten abwählen, indem der folgende Code verwendet wird, um den Wert des Switches auf `true` festzulegen:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Bei Apps, die auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, ist es möglich, da der Standardwert des Switches `true` (leere Schlüsselsequenzen werden ignoriert) lautet, sicherzustellen, dass ein Verbundschlüssel mit einem leeren Schlüssel einen Schemavalidierungsfehler generiert, indem der folgende Code zum Festlegen des Switchwerts auf `false` verwendet wird.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
