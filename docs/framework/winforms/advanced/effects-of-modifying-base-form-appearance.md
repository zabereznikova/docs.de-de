---
title: "Auswirkungen beim &#196;ndern der Darstellung von Basisformularen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Basisformulare"
  - "Vererbung, Formulare"
  - "Geerbte Formulare, Änderungen am Basisformular"
  - "Übergeordnete Formulare"
  - "Windows Forms, Basisformulardarstellung"
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Auswirkungen beim &#196;ndern der Darstellung von Basisformularen
Bei der Anwendungsentwicklung ist es häufig erforderlich, die Darstellung des Basisformulars zu ändern, dessen Merkmale an andere Formulare im aktuellen \(oder in anderen Projekten\) vererbt werden.  
  
 In der Entwurfszeit werden Änderungen an der Darstellung des Basisformulars \(z. B. durch Festlegen von Eigenschaften oder das Hinzufügen und Entfernen von Steuerelementen\) in geerbten Formularen berücksichtigt, sobald das Projekt mit dem Basisformular erstellt wird.  Es reicht nicht aus, die Änderungen am Basisformular einfach zu speichern.  Um ein Projekt zu erstellen, wählen Sie im Menü **Erstellen** die Option **Erstellen**.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Änderungen, die zur Laufzeit am Basisformular durchgeführt werden, haben keinen Einfluss auf geerbte Formulare, die bereits instantiiert sind.  
  
## Siehe auch  
 [Basis](../Topic/base%20\(C%23%20Reference\).md)   
 [Gewusst wie: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)