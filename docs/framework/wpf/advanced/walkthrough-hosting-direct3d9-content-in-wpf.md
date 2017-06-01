---
title: "Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF | Microsoft Docs"
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
  - "Direct3D9 [WPF-Interoperabilität], Hosten von Direct3D9-Inhalten"
  - "WPF, Hosten von Direct3D9-Inhalten"
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF
In dieser exemplarischen Vorgehensweise wird erläutert, wie eine WPF\-Anwendung \(Windows Presentation Foundation\) mit Direct3D9\-Inhalt gehostet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen Sie ein WPF\-Projekt, um den Direct3D9\-Inhalt zu hosten.  
  
-   Importieren Sie den Direct3D9\-Inhalt.  
  
-   Zeigen Sie den Direct3D9\-Inhalt mit der <xref:System.Windows.Interop.D3DImage>\-Klasse an.  
  
 Wenn Sie fertig sind, wissen Sie, wie Direct3D9\-Inhalt in einer WPF\-Anwendung gehostet wird.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 oder höher.  
  
-   Eine DLL, die Direct3D9\-Inhalt in einem WPF\-kompatiblen Format enthält.  Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von Direct3D9\-Inhalten zum Hosten in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## Erstellen des WPF\-Projekts  
 Zunächst muss das Projekt für die WPF\-Anwendung erstellt werden.  
  
#### So erstellen Sie das WPF\-Projekt  
  
-   Erstellen Sie in Visual C\# ein neues WPF\-Anwendungsprojekt mit dem Namen `D3DHost`.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Anwendungsprojekts](http://msdn.microsoft.com/de-de/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     Die Datei "MainWindow.xaml" wird im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] geöffnet.  
  
## Importieren des Direct3D9\-Inhalts  
 Sie importieren den Direct3D9\-Inhalt mit dem `DllImport`\-Attribut aus einer nicht verwalteten DLL.  
  
#### So importieren Sie Direct3D9\-Inhalt  
  
1.  Öffnen Sie "MainWindow.xaml.cs" im Code\-Editor.  
  
2.  Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## Hosten des Direct3D9\-Inhalts  
 Verwenden Sie schließlich die <xref:System.Windows.Interop.D3DImage>\-Klasse, um den Direct3D9\-Inhalt zu hosten.  
  
#### So hosten Sie den Direct3D9\-Inhalt  
  
1.  Ersetzen Sie in der Datei "MainWindow.xaml" das automatisch generierte XAML durch das folgende XAML.  
  
     [!code-xml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Erstellen Sie das Projekt.  
  
3.  Kopieren Sie die DLL, die den Direct3D9\-Inhalt enthält, in den Ordner bin\/Debug.  
  
4.  Drücken Sie F5, um das Projekt auszuführen.  
  
     Der Direct3D9\-Inhalt wird innerhalb der WPF\-Anwendung angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Interop.D3DImage>   
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)