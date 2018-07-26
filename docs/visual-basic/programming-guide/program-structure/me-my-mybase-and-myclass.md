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
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244711"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, "My", "MyBase" und "MyClass" in Visual Basic
`Me`, `My`, `MyBase`, und `MyClass` in Visual Basic zu erhalten, ähnliche Namen, aber unterschiedlichen Zwecken. Dieses Thema beschreibt jede dieser Entitäten, um sie voneinander zu unterscheiden.  
  
## <a name="me"></a>Me  
 Die `Me` Schlüsselwort bietet eine Möglichkeit zum Verweisen auf die jeweilige Instanz einer Klasse oder Struktur, die in der der Code derzeit ausgeführt wird. `Me` verhält sich wie entweder eine Objektvariable oder eine Strukturvariable, die auf die aktuelle Instanz verweist. Mithilfe von `Me` ist besonders nützlich für die Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder Moduls.  
  
 Nehmen wir beispielsweise an, dass Sie das folgende Verfahren in einem Modul verfügen.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Sie können diese Prozedur aufrufen und übergeben Sie die aktuelle Instanz von der <xref:System.Windows.Forms.Form> Klasse als Argument mithilfe der folgenden Anweisung.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Die `My` Funktion bietet einfachen und intuitiven Zugriff auf eine Anzahl von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klassen, mit denen des Visual Basic-Benutzers für die Interaktion mit der Computer, Anwendung, Einstellungen, Ressourcen und So weiter.  
  
## <a name="mybase"></a>MyBase  
 Die `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse. `MyBase` Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden. `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor aus Konstruktor einer abgeleiteten Klasse aufrufen.  
  
## <a name="myclass"></a>MyClass  
 Die `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, wie Sie ursprünglich implementiert. `MyClass` ist vergleichbar mit `Me`, aber alle zugehörigen Methodenaufrufe werden so behandelt, als wäre die Methode `NotOverridable`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
