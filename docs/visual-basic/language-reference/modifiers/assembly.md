---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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

