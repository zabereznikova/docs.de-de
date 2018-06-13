---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595289"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.  
  
## <a name="remarks"></a>Hinweise  
 Viele Attribute beziehen sich auf ein einzelnes Programmierelement, z. B. eine Klasse oder eine Eigenschaft. Sie solches Attribut anwenden, indem anfügen Attributblocks in spitzen Klammern (`< >`), direkt in der deklarationsanweisung.  
  
 Wenn ein Attribut nicht nur auf das folgende Element, sondern die gesamte Assembly betrifft, Sie platzieren Sie den Attributblock am Anfang der Quelldatei und identifizieren Sie das Attribut mit dem `Assembly` Schlüsselwort. Wenn sie für das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.  
  
 Sie können auch ein Attribut auf eine Assembly in der Datei AssemblyInfo.vb anwenden, in diesem Fall müssen Sie keinen Attributblock in Ihrer wichtigsten Quellcode-Datei verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)

