---
title: Assembly (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
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
ms.openlocfilehash: b496b96360ff891554ab71ba2b3227b2dabbc416
ms.lasthandoff: 03/13/2017

---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.  
  
## <a name="remarks"></a>Hinweise  
 Viele Attribute beziehen sich auf ein einzelnes Programmierelement, z. B. eine Klasse oder Eigenschaft. Sie solches Attribut anwenden, indem das Anfügen der Attributblock in spitzen Klammern (`< >`), direkt an die deklarationsanweisung.  
  
 Wenn ein Attribut nicht nur das folgende Element, sondern die gesamte Assembly betrifft, Sie stellen die Attributblock am Anfang der Quelldatei und kennzeichnen das Attribut mit dem `Assembly` Schlüsselwort. Wenn sie für das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.  
  
 Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo.vb anwenden, in diesem Fall müssen Sie nicht mit einem Attributblock in Ihrer main-Quellcodedateien.  
  
## <a name="see-also"></a>Siehe auch  
 [Modul \<Schlüsselwort >](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)


