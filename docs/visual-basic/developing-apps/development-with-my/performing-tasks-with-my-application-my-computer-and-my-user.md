---
title: "Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application object, developing applications"
  - "rapid application development (RAD), My.Application"
  - "rapid application development (RAD), My.Computer"
  - "rapid application development (RAD), My.User"
  - "My.Computer object, developing applications"
  - "My.User object, developing applications"
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Die drei zentralen `My`\-Objekte, die Zugriff auf Informationen und häufig verwendete Funktionen bereitstellen, sind `My.Application` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>\), `My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\) und `My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\).  Mit diesen Objekten können Sie auf Informationen zugreifen, die sich auf die aktuelle Anwendung, den Computer, auf dem die Anwendung installiert ist, sowie auf den aktuellen Benutzer der Anwendung beziehen.  
  
## My.Application, My.Computer und My.User  
 Die folgenden Beispiele veranschaulichen das Abrufen von Informationen mit `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_2.vb)]  
  
 Neben dem Abrufen von Informationen ermöglichen die Member, die von diesen drei Objekten bereitgestellt werden, die Ausführung von Methoden mit dem jeweiligen Objekt.  So können Sie z. B. auf eine Vielzahl an Methoden zur Manipulation von Dateien zugreifen oder die Registrierung mithilfe von `My.Computer` aktualisieren.  
  
 Datei\-E\/A\-Operationen sind mit `My` wesentlich einfacher und schneller, da es eine Reihe von Methoden und Eigenschaften für die Bearbeitung von Dateien, Verzeichnissen und Laufwerken enthält.  Mit dem <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>\-Objekt können Sie große strukturierte Dateien lesen, die Felder mit Begrenzungen oder Felder mit fester Breite enthalten.  In diesem Beispiel wird der `reader` von `TextFieldParser` geöffnet und zum Lesen von `C:\TestFolder1\test1.txt` verwendet.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_3.vb)]  
  
 Mit `My.Application` können Sie die Kultur für die Anwendung ändern.  Das folgende Beispiel veranschaulicht den Aufruf dieser Methode.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_4.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)