---
title: Me, "My", "MyBase" und "MyClass" in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bebf404cd65d1b3a2c4059d3a7c986f0157dfe2d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, "My", "MyBase" und "MyClass" in Visual Basic
`Me`, `My`, `MyBase`, und `MyClass` in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] haben ähnliche Namen aber unterschiedlichen Zwecken. In diesem Thema wird jede dieser Entitäten beschrieben, um sie voneinander zu unterscheiden.  
  
## <a name="me"></a>Me  
 Die `Me` Schlüsselwort bietet eine Möglichkeit zum Verweisen auf die jeweilige Instanz einer Klasse oder Struktur, die in der der Code derzeit ausgeführt wird. `Me`verhält sich wie eine Objektvariable oder eine Strukturvariable verweisen auf die aktuelle Instanz. Mithilfe von `Me` eignet sich besonders zur Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder eines Moduls.  
  
 Nehmen Sie beispielsweise an, dass Sie das folgende Verfahren in einem Modul verfügen.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Sie können diese Prozedur aufrufen und übergeben die aktuelle Instanz der dem <xref:System.Windows.Forms.Form> Klasse als Argument mithilfe der folgenden Anweisung.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Die `My` Feature bietet einfach und intuitiv Zugriff auf eine Anzahl von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassen der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Benutzer für die Interaktion mit dem Computer, Anwendung, Einstellungen, Ressourcen und So weiter.  
  
## <a name="mybase"></a>MyBase  
 Die `MyBase` Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse. `MyBase`Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden. `MyBase.New`wird verwendet, um explizit einen Basisklassenkonstruktor vom Konstruktor einer abgeleiteten Klasse aufrufen.  
  
## <a name="myclass"></a>MyClass  
 Die `MyClass` Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, die ursprünglich implementiert. `MyClass`ähnelt dem `Me`, aber alle zugehörigen Methodenaufrufe werden behandelt, als wäre die Methode `NotOverridable`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
