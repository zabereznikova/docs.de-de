---
title: Me, My, MyBase und MyClass in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
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
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 59dba8961712537367db9a60e8b8ba68bcb6a1ea
ms.lasthandoff: 03/13/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, "My", "MyBase" und "MyClass" in Visual Basic
`Me`, `My`, `MyBase`, und `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügen über ähnliche Namen, aber unterschiedlichen Zwecken. In diesem Thema wird jede dieser Entitäten beschrieben, um sie voneinander zu unterscheiden.  
  
## <a name="me"></a>Me  
 Die `Me` Schlüsselwort stellt eine Möglichkeit zum Verweisen auf die bestimmte Instanz einer Klasse oder Struktur, in der der Code derzeit ausgeführt wird. `Me`verhält sich wie eine Objektvariable oder eine Strukturvariable verweisen auf die aktuelle Instanz. Mithilfe von `Me` ist besonders nützlich für die Übergabe von Informationen über die derzeit ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse, Struktur oder Modul.  
  
 Nehmen wir beispielsweise an, dass Sie die folgende Prozedur in einem Modul haben.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Sie können diese Prozedur aufrufen und übergeben die aktuelle Instanz von der <xref:System.Windows.Forms.Form>Klasse als Argument mithilfe der folgenden Anweisung.</xref:System.Windows.Forms.Form>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Die `My` Funktion bietet einfachen und intuitiven Zugriff auf eine Anzahl von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Klassen die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , mit dem Computer, Anwendung, Einstellungen, Ressourcen usw. interagieren.  
  
## <a name="mybase"></a>MyBase  
 Das `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die Basisklasse der aktuellen Instanz einer Klasse. `MyBase`Member der Basisklasse zugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse gespiegelt wird häufig verwendet werden. `MyBase.New`wird verwendet, um einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.  
  
## <a name="myclass"></a>MyClass  
 Das `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable verweist auf die aktuelle Instanz einer Klasse, die gemäß der ursprünglichen Implementierung. `MyClass`ähnelt dem `Me`, aber alle Methodenaufrufe werden behandelt, als wäre die Methode `NotOverridable`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
