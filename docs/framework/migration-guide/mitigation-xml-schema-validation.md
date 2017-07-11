---
title: "Entschärfung: XML-Schema-Validierung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: abc1afb1be896740a8a74d2d8cc589269672e951
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
<a id="mitigation-xml-schema-validation" class="xliff"></a>

# Entschärfung: XML-Schema-Validierung
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ermittelt die XSD-Schemavalidierung einen Verstoß gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.  
  
<a id="impact" class="xliff"></a>

## Auswirkungen  
 Die Auswirkung dieser Änderung sollte minimal sein: In Abhängigkeit der Schemaspezifikation wir ein Schemavalidierungsfehler erwartet, wenn `xsd:unique` mithilfe eines Verbundschlüssels mit einem leeren Schlüssel verletzt wird.  
  
<a id="mitigation" class="xliff"></a>

## Problemumgehung  
 Ob ein Schemavalidierungsfehler erkannt wird, wenn ein Verbundschlüssel über einen leeren Schlüssel verfügt, kann konfiguriert werden:  
  
-   Angefangen bei den Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen, ist die Ermittlung des Schemavalidierungsfehlers standardmäßig aktiviert. Es ist jedoch möglich, dieses Verhalten abzuwählen, wodurch der Schemavalidierungsfehler nicht ermittelt wird.  
  
-   In unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführten Apps, die jedoch auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, wird eine Schemavalidierungsfehler nicht standardmäßig ermittelt. Es ist jedoch möglich, dieses Verhalten zu aktivieren, sodass der Schemavalidierungsfehler ermittelt wird.  
  
 Dieses Verhalten kann mithilfe der Klasse <xref:System.AppContext> konfiguriert werden, um den Wert des Switches `System.Xml.IgnoreEmptyKeySequences` zu definieren. Da der Standardwert des Switches `false` (leere Schlüsselsequenzen werden nicht ignoriert) lautet, können auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielende Apps dieses Verhalten abwählen, indem der folgende Code verwendet wird, um den Wert des Switches auf `true` festzulegen:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Bei Apps, die auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, ist es möglich, da der Standardwert des Switches `true` (leere Schlüsselsequenzen werden ignoriert) lautet, sicherzustellen, dass ein Verbundschlüssel mit einem leeren Schlüssel einen Schemavalidierungsfehler generiert, indem der folgende Code zum Festlegen des Switchwerts auf `false` verwendet wird.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
<a id="see-also" class="xliff"></a>

## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
