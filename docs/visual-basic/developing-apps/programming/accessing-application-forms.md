---
title: "Accessing Application Forms (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "forms, communicating between"
  - "application forms, accessing"
  - "forms, accessing one from another"
  - "My.Forms object"
  - "forms, accessing all open"
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Accessing Application Forms (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das `My.Forms`\-Objekt stellt eine einfache Möglichkeit des Zugriffs auf eine Instanz jedes Windows\-Formulare bereit, das im Projekt der Anwendung deklariert ist.  Sie können auch mit den Eigenschaften des `My.Application`\-Objekts auf das Formular für den Begrüßungsbildschirm und das Hauptformular der Anwendung zugreifen und eine Liste der offenen Formulare der Anwendung abrufen.  
  
## Aufgaben  
 In der folgenden Tabelle werden Beispiele aufgeführt, die den Zugriff auf die Formulare einer Anwendung veranschaulichen.  
  
|||  
|-|-|  
|To|Siehe|  
|Zugriff auf ein Formular über ein anderes Formular in einer Anwendung|[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|Anzeigen der Titel aller geöffneten Formulare der Anwendung|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|Aktualisieren des Begrüßungsbildschirms mit Statusinformationen beim Start der Anwendung|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)