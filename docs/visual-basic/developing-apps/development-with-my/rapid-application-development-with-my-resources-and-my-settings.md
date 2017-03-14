---
title: "Rapid Application Development with My.Resources and My.Settings (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object, developing applications"
  - "rapid application development (RAD), My.Resources"
  - "rapid application development (RAD), My.Settings"
  - "My.Resources object, developing applications"
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Rapid Application Development with My.Resources and My.Settings (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Das `My.Resources`\-Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und das dynamische Abrufen von Ressourcen für die Anwendung.  
  
## Abrufen von Ressourcen  
 Eine Reihe von Ressourcen wie Audiodateien, Symbole, Bilder und Zeichenfolgen kann mit dem `My.Resources`\-Objekt abgerufen werden.  So können Sie z. B. auf die kulturspezifischen Ressourcendateien der Anwendung zugreifen.  Im folgenden Beispiel wird das Symbol des Formulars auf das Symbol mit dem Namen `Form1Icon` festgelegt, das in der Ressourcendatei der Anwendung gespeichert ist.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 Das `My.Resources`\-Objekt macht nur globale Ressourcen verfügbar.  Es stellt keinen Zugriff auf Formularen zugeordnete Ressourcendateien bereit.  Sie müssen auf die Formularressourcen vom Formular aus zugreifen.  Weitere Informationen finden Sie unter [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/de-de/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Ebenso bietet das `My.Settings`\-Objekt Zugriff auf die Anwendungseinstellungen und ermöglicht es, die Eigenschafteneinstellungen und andere Informationen über die Anwendung dynamisch zu speichern und abzurufen.  Weitere Informationen finden Sie unter [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## Siehe auch  
 [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md)   
 [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Accessing Application Settings](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)