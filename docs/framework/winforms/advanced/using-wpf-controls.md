---
title: "Verwenden von WPF-Steuerelementen | Microsoft Docs"
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
  - "Interoperabilität [WPF]"
  - "Windows Forms-Designer, Interoperabilität mit WPF"
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Verwenden von WPF-Steuerelementen
Sie können WPF \(Windows Presentation Foundation\)\-Steuerelemente in Windows Forms\-basierten Anwendungen verwenden.  Obwohl es sich dabei um zwei unterschiedliche Anzeigetechnologien handelt, arbeiten diese reibungslos zusammen.  
  
 Der Windows Forms\-Designer stellt eine visuelle Entwurfsumgebung zum Hosten von Windows Presentation Foundation\-Steuerelementen bereit.  Ein WPF\-Steuerelement wird von einem speziellen Windows Forms\-Steuerelement mit dem Namen <xref:System.Windows.Forms.Integration.ElementHost> gehostet.  Über dieses Steuerelement wird das WPF\-Steuerelement zu einem Teil des Formularlayouts und empfängt Tastatur\- und Mausmeldungen.  Zur Entwurfszeit können Sie das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement wie jedes andere Windows Forms\-Steuerelement anordnen.  
  
 Sie können auch Windows Forms\-Steuerelemente in den WPF\-basierten Anwendungen verwenden.  Weitere Informationen finden Sie unter [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## In diesem Abschnitt  
 [Gewusst wie: Kopieren und Einfügen eines ElementHost\-Steuerelements zur Entwurfszeit](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Veranschaulicht das Kopieren eines Windows Presentation Foundation\-Steuerelements in ein Windows Form.  
  
 [Exemplarische Vorgehensweise: Anordnen von WPF\-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Veranschaulicht die Verwendung von Windows Forms\-Layoutfeatures, z. B. Verankern und Ausrichtungslinien, zum Anordnen von Windows Presentation Foundation\-Steuerelementen.  
  
 [Exemplarische Vorgehensweise: Ändern von Eigenschaften eines gehosteten WPF\-Elements zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Veranschaulicht den Workflow, der beim Ändern von Eigenschaften für WPF\-Steuerelemente zwischen dem Windows Forms\-Designer und [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] abläuft.  
  
 [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Veranschaulicht das Erstellen eines Windows Presentation Foundation\-Steuerelements zur Verwendung in Windows Forms\-basierten Anwendungen.  
  
 [Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost\-Steuerelements in separate Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Veranschaulicht das Kopieren eines Windows Presentation Foundation\-Steuerelements zwischen zwei Windows Forms.  
  
 [Exemplarische Vorgehensweise: Zuweisen von WPF\-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Veranschaulicht das Auswählen der Windows Presentation Foundation\-Steuerelementtypen, die im Formular angezeigt werden sollen.  
  
 [Exemplarische Vorgehensweise: Formatieren von WPF\-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Veranschaulicht den Workflow, der beim Anwenden von Stilen auf Windows Presentation Foundation\-Steuerelemente zwischen Windows Forms\-Designer und [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] abläuft.  
  
## Referenz  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Beschreibt eine Klasse, die Sie zum Hosten von Windows Presentation Foundation\-Steuerelementen in Windows Forms\-basierten Anwendungen verwenden können.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Beschreibt eine Klasse, die Sie zum Hosten von Windows Forms\-Steuerelementen in Windows Presentation Foundation\-basierten Anwendungen verwenden können.  
  
## Verwandte Abschnitte  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Beschreibt die Interoperation zwischen Windows Presentation Foundation\- und Windows Forms\-Technologie  
  
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)  
 Beschreibt das Entwerfen von Windows Presentation Foundation\-Steuerelementen in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].