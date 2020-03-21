---
title: Me, My, MyBase und MyClass
ms.date: 07/20/2015
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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401430"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, "My", "MyBase" und "MyClass" in Visual Basic
`Me`, `My` `MyBase`, `MyClass` und in Visual Basic haben ähnliche Namen, aber unterschiedliche Zwecke. In diesem Thema werden die einzelnen Entitäten beschrieben, um sie zu unterscheiden.  
  
## <a name="me"></a>Bei mir selbst  
 Das `Me` Schlüsselwort bietet eine Möglichkeit, auf die spezifische Instanz einer Klasse oder Struktur zu verweisen, in der der Code gerade ausgeführt wird. `Me`verhält sich wie eine Objektvariable oder eine Strukturvariable, die sich auf die aktuelle Instanz bezieht. Die `Me` Verwendung ist besonders nützlich, um Informationen über die aktuell ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder einem Anderen Modul weiterzugeben.  
  
 Angenommen, Sie haben das folgende Verfahren in einem Modul.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Sie können diese Prozedur aufrufen und <xref:System.Windows.Forms.Form> die aktuelle Instanz der Klasse als Argument übergeben, indem Sie die folgende Anweisung verwenden.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Die `My` Funktion bietet einfachen und intuitiven Zugriff auf eine Reihe von .NET Framework-Klassen, sodass der Visual Basic-Benutzer mit dem Computer, der Anwendung, den Einstellungen, den Ressourcen usw. interagieren kann.  
  
## <a name="mybase"></a>MyBase  
 Das `MyBase` Schlüsselwort verhält sich wie eine Objektvariable, die sich auf die Basisklasse der aktuellen Instanz einer Klasse bezieht. `MyBase`wird häufig für den Zugriff auf Basisklassenmember verwendet, die in einer abgeleiteten Klasse überschrieben oder überschattet werden. `MyBase.New`wird verwendet, um explizit einen Basisklassenkonstruktor von einem abgeleiteten Klassenkonstruktor aufzurufen.  
  
## <a name="myclass"></a>MyClass  
 Das `MyClass` Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse verweist, wie sie ursprünglich implementiert wurde. `MyClass`ist ähnlich `Me`wie , aber alle Methodenaufrufe werden `NotOverridable`so behandelt, als wäre die Methode .  
  
## <a name="see-also"></a>Weitere Informationen

- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
