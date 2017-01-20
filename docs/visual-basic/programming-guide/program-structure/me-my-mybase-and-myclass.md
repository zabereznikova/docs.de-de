---
title: "Me, My, MyBase, and MyClass in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MyClass"
  - "vb.Me"
  - "MyBase"
  - "vb.MyBase"
  - "Me"
  - "vb.MyClass"
  - "vb.This"
  - "vb.My"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My object"
  - "self-reference, Me keyword"
  - "MyClass keyword, relationship to similar programming elements"
  - "Me keyword, relationship to similar programming elements"
  - "Me keyword, referring to the current instance of an object"
  - "Me keyword"
  - "self-reference"
  - "current instance, Me keyword"
  - "MyBase keyword, relationship to similar programming elements"
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Me, My, MyBase, and MyClass in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Me`, `My`, `MyBase` und `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] weisen ähnliche Namen auf, werden jedoch zu unterschiedlichen Zwecken verwendet.  In diesem Thema wird jede dieser Entitäten beschrieben, um die Unterschiede zu erläutern.  
  
## Me  
 Das `Me`\-Schlüsselwort ermöglicht einen Verweis auf die bestimmte Instanz einer Klasse oder Struktur, in der der Code momentan ausgeführt wird.  Das `Me`\-Schlüsselwort verhält sich wie eine Objektvariable oder eine Strukturvariable, die auf die aktuelle Instanz verweist.  `Me` ist vor allem bei der Übergabe von Informationen über die momentan ausgeführte Instanz einer Klasse oder Struktur an eine Prozedur in einer anderen Klasse oder Struktur oder in einem anderen Modul hilfreich.  
  
 Beispiel: Ein Modul enthält die folgende Prozedur.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Sie können diese Prozedur aufrufen und die aktuelle Instanz der <xref:System.Windows.Forms.Form>\-Klasse mithilfe der folgenden Anweisung als Argument übergeben.  
  
```  
ChangeFormColor(Me)  
```  
  
## My  
 Die `My`\-Funktion ermöglicht es, einfach und intuitiv auf eine Reihe von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassen zuzugreifen, sodass der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Benutzer mit dem Computer, der Anwendung, mit Einstellungen, Ressourcen usw. interagieren kann.  
  
## MyBase  
 Das `MyBase`\-Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist.  `MyBase` wird häufig für den Zugriff auf Basisklassenmember verwendet, die in einer abgeleiteten Klasse überschrieben werden oder für die ein Shadowing durchgeführt wird.  `MyBase.New` dient dazu, Basisklassenkonstruktoren aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.  
  
## MyClass  
 Das `MyClass`\-Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Klasseninstanz gemäß der ursprünglichen Implementierung verweist.  `MyClass` ist mit `Me` vergleichbar, alle zugehörigen Methodenaufrufe werden jedoch so behandelt, als wäre die aufgerufene Methode `NotOverridable`.  
  
## Siehe auch  
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)