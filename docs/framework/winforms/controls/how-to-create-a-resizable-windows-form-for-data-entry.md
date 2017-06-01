---
title: "Gewusst wie: Erstellen von in der Gr&#246;&#223;e ver&#228;nderbaren Windows Forms f&#252;r die Dateneingabe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Formulare, Erstellen von Formularen mit veränderlicher Größe"
  - "Layout [Windows Forms], Größenänderung"
  - "TableLayoutPanel-Steuerelement [Windows Forms]"
  - "Windows Forms, Größenveränderbar"
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen von in der Gr&#246;&#223;e ver&#228;nderbaren Windows Forms f&#252;r die Dateneingabe
Ein gutes Layout reagiert angemessen auf Änderungen in den Dimensionen des übergeordneten Formulars.  Sie können das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement verwenden, um das Layout Ihres Formulars so zu gestalten, dass die Größe und die Position Ihrer Steuerelemente auf konsistente Weise geändert werden, wenn sich die Dimensionen des Formulars ändern.  Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ist auch nützlich, wenn Änderungen am Inhalt Ihrer Steuerelemente Änderungen im Layout verursachen.  Der in diesem Verfahren beschriebene Vorgang kann innerhalb der Visual Studio\-Umgebung ausgeführt werden.  Siehe auch [Exemplarische Vorgehensweise: Erstellen eines in der Größe veränderbaren Windows Forms für die Dateneingabe](http://msdn.microsoft.com/library/991eahec%20\(v=vs.110\)).  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement zum Erstellen eines Layouts verwendet wird, das angemessen reagiert, wenn der Benutzer die Größe des Formulars ändert.  Außerdem wird ein Layout gezeigt, das für Lokalisierung gut geeignet ist.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Gewusst wie: Entwerfen eines Windows Forms\-Layouts, das zur Lokalisierung gut geeignet ist](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)   
 [Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)