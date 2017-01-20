---
title: "A startup form has not been specified | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_NoStartupForm"
dev_langs: 
  - "VB"
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# A startup form has not been specified
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Anwendung verwendet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>\-Klasse, gibt jedoch kein Startformular an.  
  
 Dieser Fehler kann auftreten, wenn im Projekt\-Designer das Kontrollkästchen **Anwendungsframework aktivieren** aktiviert ist, jedoch kein **Startformular** angegeben wurde.  Weitere Informationen finden Sie unter [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie ein Startobjekt für die Anwendung an.  
  
     Weitere Informationen finden Sie unter [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Überschreiben Sie die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>\-Methode, um die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>\-Eigenschaft auf das Startformular festzulegen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>   
 [Overview of the Visual Basic Application Model](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)