---
title: "Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic) | Microsoft Docs"
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
  - "My.WebServices object, developing applications"
  - "My.Forms object, developing applications"
  - "rapid application development (RAD), My.Forms"
  - "rapid application development (RAD), My.WebServices"
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)\-Objekt und das [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)\-Objekt bieten Zugriff auf die von der Anwendung verwendeten Formulare, Datenquellen und XML\-Webdienste.  Dazu werden Auflistungen der *Standardinstanzen* von jedem dieser Objekte bereitgestellt.  
  
## Standardinstanzen  
 Eine Standardinstanz ist eine Instanz der Klasse, die von der Laufzeit bereitgestellt wird und nicht mithilfe der `Dim`\-Anweisung und der `New`\-Anweisung deklariert und instanziiert werden muss.  Das folgende Beispiel veranschaulicht eine Möglichkeit der Deklaration und Instanziierung einer <xref:System.Windows.Forms.Form>\-Klasse mit dem Namen `Form1` und den anschließenden Abruf einer Standardinstanz dieser <xref:System.Windows.Forms.Form>\-Klasse mithilfe von `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-pr_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-pr_2.vb)]  
  
 Das `My.Forms`\-Objekt gibt eine Auflistung von Standardinstanzen für jede im Projekt vorhandene `Form`\-Klasse zurück.  Ebenso stellt `My.WebServices` eine Standardinstanz der Proxyklasse für jeden Webdienst bereit, der Ziel eines in der Anwendung enthaltenen Verweises ist.  
  
## Siehe auch  
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)