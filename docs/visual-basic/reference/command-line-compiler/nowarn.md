---
title: "/nowarn | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nowarn compiler option [Visual Basic]"
  - "/nowarn compiler option [Visual Basic]"
  - "-nowarn compiler option [Visual Basic]"
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /nowarn
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Unterdrückt die Compilerfunktion zum Erstellen von Warnungen.  
  
## Syntax  
  
```  
/nowarn[:numberList]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`numberList`|Optional.  Durch Kommas getrennte Liste der Warnungs\-ID\-Nummern, die vom Compiler unterdrückt werden sollen.  Wenn keine Warnungs\-IDs angegeben werden, werden alle Warnungen unterdrückt.|  
  
## Hinweise  
 Die `/nowarn`\-Option bewirkt, dass der Compiler keine Warnungen generiert.  Um eine einzelne Warnung zu unterdrücken, geben Sie die Warnungs\-ID bei der `/nowarn`\-Option nach dem Doppelpunkt an.  Trennen Sie mehrere Warnungsnummern jeweils durch ein Komma voneinander.  
  
 Sie müssen lediglich den numerischen Teil des Warnungsbezeichners angeben.  Wenn Sie z. B. BC42024 \(die Warnung für nicht verwendete lokale Variablen\) unterdrücken möchten, geben Sie `/nowarn:42024` an.  
  
 Weitere Informationen über die Warnungs\-ID\-Nummern finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
||  
|-|  
|So legen Sie \/nowarn in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**, um alle Warnungen zu deaktivieren.<br />     \- oder \-<br />     Um eine bestimmte Warnung zu deaktivieren, klicken Sie in der Dropdownliste neben der Warnung auf **Keine**.|  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert. Warnungen werden nicht angezeigt.  
  
```  
vbc /nowarn t2.vb  
```  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert. Warnungen für nicht verwendete lokale Variablen \(42024\) werden nicht angezeigt.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic)