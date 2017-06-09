---
title: "Mauszeiger in Windows Forms | Microsoft Docs"
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
  - "Cursor, Einstellen [Windows Forms]"
  - "Mauscursor"
  - "Mauszeiger"
  - "Mauszeiger, Einstellen [Windows Forms]"
  - "Maus, Cursor"
  - "Zeiger, Einstellen [Windows Forms]"
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Mauszeiger in Windows Forms
Der *Mauszeiger*, der manchmal auch als Cursor bezeichnet wird, ist eine Bitmap, die einen Fokuspunkt auf dem Bildschirm für Benutzereingaben mit der Maus festlegt.  Dieses Thema enthält eine Übersicht über den Mauszeiger in Windows Forms und beschreibt einige Möglichkeiten, den Mauszeiger zu ändern und zu steuern.  
  
## Zugreifen auf den Mauszeiger  
 Der Mauszeiger wird durch die <xref:System.Windows.Forms.Cursor>\-Klasse dargestellt, und jedes <xref:System.Windows.Forms.Control> verfügt über eine <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName>\-Eigenschaft, die den Zeiger für dieses Steuerelement festlegt.  Die <xref:System.Windows.Forms.Cursor>\-Klasse enthält Eigenschaften, die den Zeiger beschreiben, z. B. die <xref:System.Windows.Forms.Cursor.Position%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Cursor.HotSpot%2A>\-Eigenschaft, sowie Methoden, die die Darstellung des Zeigers ändern können, z. B. die Methoden <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A> und <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## Steuern des Mauszeigers  
 Mitunter möchten Sie den Bereich begrenzen, in dem der Mauszeiger verwendet werden kann, oder die Position der Maus ändern.  Sie können die aktuelle Position der Maus mithilfe der <xref:System.Windows.Forms.Cursor.Position%2A>\-Eigenschaft von <xref:System.Windows.Forms.Cursor> abrufen oder festlegen.  Außerdem können Sie den Bereich begrenzen, in dem der Mauszeiger verwendet werden kann, indem Sie die <xref:System.Windows.Forms.Cursor.Clip%2A>\-Eigenschaft festlegen.  Der Clipbereich ist standardmäßig der gesamte Bildschirm.  
  
## Ändern des Mauszeigers  
 Das Ändern des Mauszeigers ist eine wichtige Möglichkeit, dem Benutzer Feedback bereitzustellen.  Beispielsweise kann der Mauszeiger in den Handlern des <xref:System.Windows.Forms.Control.MouseEnter>\-Ereignisses und des <xref:System.Windows.Forms.Control.MouseLeave>\-Ereignisses geändert werden, um dem Benutzer mitzuteilen, dass Berechnungen vorgenommen werden, und um die Interaktion des Benutzers im Steuerelement zu beschränken.  In manchen Situationen ändert sich der Mauszeiger aufgrund von Systemereignissen, beispielsweise bei einer Drag & Drop\-Operation in einer Anwendung.  
  
 Das Ändern des Mauszeigers erfolgt in erster Linie dadurch, dass die <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=fullName>\-Eigenschaft oder die <xref:System.Windows.Forms.Control.DefaultCursor%2A>\-Eigenschaft eines Steuerelements auf einen neuen <xref:System.Windows.Forms.Cursor> festgelegt wird.  Beispiele zum Ändern des Mauszeigers finden Sie im Codebeispiel in der <xref:System.Windows.Forms.Cursor>\-Klasse.  Darüber hinaus macht die <xref:System.Windows.Forms.Cursors>\-Klasse eine Reihe von <xref:System.Windows.Forms.Cursor>\-Objekten für viele verschiedene Zeigertypen verfügbar, z. B. einen Zeiger in Form einer Hand.  Um den Wartezeiger anzuzeigen, der wie eine Sanduhr aussieht, verwenden Sie die <xref:System.Windows.Forms.Control.UseWaitCursor%2A>\-Eigenschaft der <xref:System.Windows.Forms.Control>\-Klasse, wenn sich der Mauszeiger auf dem Steuerelement befindet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Cursor>   
 [Mauseingabe in einer Windows Forms\-Anwendung](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Drag & Drop\-Funktionen in Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)