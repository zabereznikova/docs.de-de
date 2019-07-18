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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801986"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Gibt an, dass ein Attribut am Anfang einer Quelldatei für die gesamte Assembly gilt.  
  
## <a name="remarks"></a>Hinweise  
 Viele Attribute beziehen sich auf ein bestimmtes Programmierelement, z. B. eine Klasse oder Eigenschaft. Sie ein solches Attribut anwenden, durch Anfügen des Attributblocks in spitzen Klammern (`< >`), direkt in der deklarationsanweisung.  
  
 Wenn ein Attribut nicht nur auf das folgende Element, sondern für die gesamte Assembly betrifft, Sie platzieren Sie den Attributblock am Anfang der Quelldatei und identifizieren Sie das Attribut mit dem `Assembly` Schlüsselwort. Wenn es sich um das aktuelle Assemblymodul gilt, verwenden Sie die [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) Schlüsselwort.  
  
 Sie können auch ein Attribut auf eine Assembly in der AssemblyInfo.vb-Datei anwenden, in diesem Fall müssen Sie nicht mit einem Attributblock in Ihrer main Quelle-Codedatei.  
  
## <a name="see-also"></a>Siehe auch

- [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
