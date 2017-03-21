---
title: '&quot;&lt;Attribut&gt;&quot; kann nicht angewendet werden, da das Format der GUID &quot;&lt;Anzahl&gt;&quot; ist nicht korrekt | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32500
- bc32500
dev_langs:
- VB
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f22f9ecd63582e2a346702919cf9154819b8eb0e
ms.lasthandoff: 03/13/2017

---
# <a name="39ltattributegt39-cannot-be-applied-because-the-format-of-the-guid-39ltnumbergt39-is-not-correct"></a>'&lt;Attribut&gt;' kann nicht angewendet werden, da das Format der GUID '&lt;Anzahl&gt;' ist ungültig
Ein `COMClassAttribute` gibt eine GUID (globally unique Identifier), die nicht das richtige Format für eine GUID entspricht. `COMClassAttribute`nutzt GUIDs zur Identifizierung der Klasse, die Schnittstelle und die.  
  
 Eine GUID besteht aus 16 Bytes, von denen die ersten acht numerisch und die letzten acht binär sind. Er ist wird von Microsoft-Dienstprogrammen wie uuidgen.exe generiert und in Raum und Zeit eindeutig sein.  
  
 **Fehler-ID:** BC32500  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen der richtigen GUID oder GUIDs zur Identifizierung des COM-Objekts erforderlich.  
  
2.  Stellen Sie sicher, dass die GUID-Zeichenfolgen, die dem `COMClassAttribute` -Attributblock angezeigt werden, ordnungsgemäß kopiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Guid></xref:System.Guid>   
[Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)


