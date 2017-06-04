---
title: "Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [WPF-Interoperabilität]"
  - "Hosting von ActiveX-Steuerelementen"
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF
Um eine verbesserte Interaktion mit Browsern zu ermöglichen, können Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]\-Steuerelemente in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendung verwenden.  Diese exemplarische Vorgehensweise veranschaulicht, wie Sie [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] als Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite hosten können.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Erstellen des ActiveX\-Steuerelements  
  
-   Hosten des ActiveX\-Steuerelements auf einer WPF\-Seite  
  
 Am Ende dieser exemplarischen Vorgehensweise verstehen Sie, wie Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]\-Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendungen verwenden.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] muss auf dem Computer installiert sein, auf dem [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] installiert ist.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Erstellen des Projekts  
  
#### So erstellen Sie das Projekt und richten es ein  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.  
  
2.  Fügen Sie der Projektmappe ein Windows Forms\-Steuerelementbibliothek\-Projekt hinzu, und geben Sie für das Projekt den Namen `WmpAxLib` ein.  
  
3.  Fügen Sie im Projekt "WmpAxLib" einen Verweis auf die Windows Media Player\-Assembly \(wmp.dll\) hinzu.  
  
4.  Öffnen Sie die **Toolbox**.  
  
5.  Klicken Sie mit der rechten Maustaste auf die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.  
  
6.  Klicken Sie auf die Registerkarte **COM\-Steuerelemente**, wählen Sie das **Windows Media Player**\-Steuerelement aus, und klicken Sie anschließend auf **OK**.  
  
     Das Windows Media Player\-Steuerelement wird der **Toolbox** hinzugefügt.  
  
7.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf die **UserControl1**\-Datei, und klicken Sie dann auf **Umbenennen**.  
  
8.  Ändern Sie den Namen je nach Programmiersprache in `WmpAxControl.vb` oder `WmpAxControl.cs`.  
  
9. Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.  
  
## Erstellen des ActiveX\-Steuerelements  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] generiert automatisch eine <xref:System.Windows.Forms.AxHost>\-Wrapperklasse für ein [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)]\-Steuerelement, wenn das Steuerelement einer Entwurfsoberfläche hinzugefügt wird.  Das folgende Verfahren erstellt eine verwaltete Assembly mit dem Namen AxInterop.WMPLib.dll.  
  
#### So erstellen Sie das ActiveX\-Steuerelement  
  
1.  Öffnen Sie "WmpAxControl.vb" oder "WmpAxControl.cs" im Windows Forms\-Designer.  
  
2.  Fügen Sie das Windows Media Player\-Steuerelement aus der **Toolbox** der Entwurfsoberfläche hinzu.  
  
3.  Legen Sie im Eigenschaftenfenster den Wert der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft des Windows Media Player\-Steuerelements auf <xref:System.Windows.Forms.DockStyle> fest.  
  
4.  Erstellen Sie das Steuerelementbibliothek\-Projekt "WmpAxLib".  
  
## Hosten des ActiveX\-Steuerelements auf einer WPF\-Seite  
  
#### So hosten Sie das ActiveX\-Steuerelement  
  
1.  Fügen Sie im HostingAxInWpf\-Projekt einen Verweis auf die generierte [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)]\-Interoperabilitätsassembly hinzu.  
  
     Diese Assembly heißt "AxInterop.WMPLib.dll" und wurde dem Ordner "Debug" des Projekts "WmpAxLib" hinzugefügt, als Sie das Windows Media Player\-Steuerelement importiert haben.  
  
2.  Fügen Sie einen Verweis auf die WindowsFormsIntegration\-Assembly, die WindowsFormsIntegration.dll genannt wird, hinzu.  
  
3.  Fügen Sie einen Verweis auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Assembly, die System.Windows.Forms.dll genannt wird, hinzu.  
  
4.  Öffnen Sie "MainWindow.xaml" im WPF\-Designer.  
  
5.  Geben Sie für das <xref:System.Windows.Controls.Grid>\-Element den Namen `grid1` ein.  
  
     [!code-xml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  Wählen Sie in der Designansicht oder XAML\-Ansicht das <xref:System.Windows.Window>\-Element aus.  
  
7.  Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse**.  
  
8.  Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis.  
  
9. Fügen Sie folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis zu behandeln.  
  
     In diesem Code wird eine Instanz des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelements erstellt und eine Instanz des `AxWindowsMediaPlayer`\-Steuerelements als untergeordnetes Element hinzugefügt.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)