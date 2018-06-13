---
title: Me, "My", "MyBase" und "MyClass" in Visual Basic
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
ms.openlocfilehash: f3db5f8f6688e68992f683ac1b1465078aa41231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650526"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, "My", "MyBase" und "MyClass" in Visual Basic
`Me`, `My`, `MyBase`, und `MyClass` in Visual Basic haben ähnliche Namen aber unterschiedlichen Zwecken. In diesem Thema wird jede dieser Entitäten beschrieben, um sie voneinander zu unterscheiden.  
  
## <a name="me"></a>Me  
 Die `Me` Schlüsselwort bietet eine Möglichkeit zum Verweisen auf die jeweilige Instanz einer Klasse oder Struktur, die in der der Code derzeit ausgeführt wird. `Me` verhält sich wie eine Objektvariable oder eine Strukturvariable verweisen auf die aktuelle Instanz. Mithilfe von `Me` eignet sich besonders zur Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder eines Moduls.  
  
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
 Die `My` Feature bietet einfach und intuitiv Zugriff auf eine Anzahl von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klassen, damit der Visual Basic-Benutzer für die Interaktion mit dem Computer, Anwendung, Einstellungen, Ressourcen usw.  
  
## <a name="mybase"></a>MyBase  
 Die `MyBase` Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse. `MyBase` Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden. `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor vom Konstruktor einer abgeleiteten Klasse aufrufen.  
  
## <a name="myclass"></a>MyClass  
 Die `MyClass` Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, die ursprünglich implementiert. `MyClass` ähnelt dem `Me`, aber alle zugehörigen Methodenaufrufe werden behandelt, als wäre die Methode `NotOverridable`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
