---
title: "/errorreport | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-errorreport compiler option [Visual Basic]"
  - "/errorreport compiler option [Visual Basic]"
  - "errorreport compiler option [Visual Basic]"
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /errorreport
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, wie der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler interne Compilerfehler meldet.  
  
## Syntax  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## Hinweise  
 Diese Option bietet eine komfortable Möglichkeit, einen internen Compilerfehler \(ICE, Internal Compiler Error\) von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] dem [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Team von Microsoft mitzuteilen.  Standardmäßig sendet der Compiler keine Informationen an Microsoft.  Wenn jedoch ein interner Compilerfehler auftritt, ermöglicht es Ihnen diese Option, den Fehler Microsoft mitzuteilen.  Diese Informationen erleichtern es den Microsoft\-Technikern, die Ursache zu identifizieren und die nächste Version von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] entsprechend zu verbessern.  
  
 Ob Benutzer Berichte versenden können, ist vom Computer und den Benutzerberechtigungen abhängig.  
  
 In der folgenden Tabelle wird die Wirkung der `/errorreport`\-Option zusammengefasst.  
  
|||  
|-|-|  
|Option|Verhalten|  
|`prompt`|Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld eingeblendet, in dem die Daten genau angezeigt werden, die vom Compiler erfasst wurden.  Sie können bestimmen, ob der Fehlerbericht vertrauliche Daten enthält, und entscheiden, ob er an Microsoft gesendet werden soll.  Wenn Sie den Bericht senden möchten und die Computer\- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.|  
|`queue`|Reiht den Fehlerbericht in eine Warteschlange ein.  Wenn Sie sich mit Administratorberechtigungen anmelden, können Sie alle Fehler seit der letzten Anmeldung angeben \(Sie werden nur etwa alle drei Tage einmal dazu aufgefordert, Fehlerberichte zu senden\).  Dies ist das Standardverhalten, wenn die `/errorreport`\-Option nicht angegeben wurde.|  
|`send`|Wenn ein interner Compilerfehler auftritt und die Computer\- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.<br /><br /> Die Option `/errorReport:send` versucht automatisch, Fehlerinformationen an Microsoft zu senden.  Diese Option hängt von der Registrierung ab.  Weitere Informationen zur Einstellung der entsprechenden Werte in der Registrierung finden Sie unter [Aktivieren der automatischen Fehlerberichtertstattung in Visual Studio 2008\-Befehlszeilentools](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Wenn ein interner Compilerfehler auftritt, wird er nicht erfasst und nicht an Microsoft gesendet.|  
  
 Zu den vom Compiler gesendeten Daten zählt der Stapel zum Zeitpunkt des Fehlers. Diese Daten umfassen i. d. R. Quellcode.  Bei Verwendung von `/errorreport` mit der[\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)\-Option wird die gesamte Quelldatei gesendet.  
  
 Es empfiehlt sich, die Option zusammen mit der [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)\-Option zu verwenden, da die Microsoft\-Techniker so den Fehler einfacher reproduzieren können.  
  
> [!NOTE]
>  Die Option `/errorreport` ist nicht innerhalb der Entwicklungsumgebung von Visual Studio verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Im folgenden Code wird versucht, `T2.vb` zu kompilieren, und wenn der Compiler auf einen internen Compilerfehler trifft, werden Sie gebeten, den Fehlerbericht an Microsoft zu senden.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)