---
title: Verwenden von WPF-Steuerelementen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8225447e6c0daa7894d622616131febb6ac82b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="using-wpf-controls"></a>Verwenden von WPF-Steuerelementen
Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden. Obwohl diese zwei unterschiedliche Ansicht Technologien sind, zusammenarbeiten sie reibungslos.  
  
 Windows Forms-Designer bietet eine visuelle entwurfsumgebung zum Hosten von Windows Presentation Foundation-Steuerelemente. Ein WPF-Steuerelement gehostet wird, von einem speziellen Windows Forms-Steuerelement mit dem Namen <xref:System.Windows.Forms.Integration.ElementHost>. Dieses Steuerelement ermöglicht das WPF-Steuerelement zur Teilnahme an der das Formularlayout und zum Empfangen von Nachrichten von Tastatur und Maus. Sie können zur Entwurfszeit Anordnen der <xref:System.Windows.Forms.Integration.ElementHost> steuern, wie Sie jedes Windows Forms-Steuerelement.  
  
 Sie können auch Windows Forms-Steuerelemente in Ihrer WPF-basierten Anwendungen. Weitere Informationen finden Sie unter [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Veranschaulicht das Kopieren eines Windows Presentation Foundation-Steuerelements in einem Windows Form.  
  
 [Exemplarische Vorgehensweise: Anordnen von WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Zeigt, wie Windows Forms-Layoutfunktionen, z. B. Verankern und Ausrichtungslinien, zum Anordnen von Windows Presentation Foundation-Steuerelementen.  
  
 [Exemplarische Vorgehensweise: Ändern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Zeigt den Workflow zwischen Windows Forms-Designer und der [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] zum Ändern von Eigenschaften auf WPF-Steuerelemente.  
  
 [Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Zeigt, wie ein Windows Presentation Foundation-Steuerelement für die Verwendung in Windows Forms-basierten Anwendungen zu erstellen.  
  
 [Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements in separate Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Zeigt, wie ein Windows Presentation Foundation-Steuerelement von einem Windows Form in eine andere kopieren.  
  
 [Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Zeigt, wie die Windows Presentation Foundation-Steuerelementtypen auswählen, die auf dem Formular angezeigt werden soll.  
  
 [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Zeigt den Workflow zwischen Windows Forms-Designer und der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] zum Anwenden von Stilen auf Steuerelemente für Windows Presentation Foundation.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Beschreibt eine Klasse, die zum Hosten von Windows Presentation Foundation-Steuerelementen in Windows Forms-basierten Anwendungen verwendet werden können.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Beschreibt eine Klasse, die Sie zum Hosten von Windows Forms-Steuerelementen in einer Windows Presentation Foundation-basierten Anwendung verwenden können.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Beschreibt die Interoperation zwischen der Windows Presentation Foundation und Windows Forms-Technologien.  
  
 [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 Beschreibt das Entwerfen von Windows Presentation Foundation-Steuerelemente in Visual Studio.
