---
title: 'Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10558348a963f0b243dcfbe23171f6e24da6da0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF
In dieser exemplarischen Vorgehensweise zeigt, wie Direct3D9-Inhalt in eine Windows Presentation Foundation (WPF)-Anwendung gehostet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen Sie ein WPF-Projekt, um den Direct3D9-Inhalt hosten.  
  
-   Importieren Sie den Direct3D9-Inhalt.  
  
-   Zeigt den Inhalt der Direct3D9 mithilfe der <xref:System.Windows.Interop.D3DImage> Klasse.  
  
 Wenn Sie fertig sind, wissen Sie, wie Direct3D9-Inhalt in einer WPF-Anwendung gehostet wird.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
-   DirectX SDK 9 oder höher.  
  
-   Eine DLL, die Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält. Weitere Informationen finden Sie unter [WPF und Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Erstellen des WPF-Projekts  
 Der erste Schritt ist zum Erstellen des Projekts für die WPF-Anwendung.  
  
#### <a name="to-create-the-wpf-project"></a>So erstellen Sie das WPF-Projekt  
  
-   Erstellen ein neues WPF-Anwendungsprojekts in Visual c# mit dem Namen `D3DHost`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     "MainWindow.xaml" wird geöffnet, der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>Importieren den Direct3D9-Inhalt  
 Sie importieren die Direct3D9-Inhalte aus einer nicht verwalteten DLL mithilfe der `DllImport` Attribut.  
  
#### <a name="to-import-direct3d9-content"></a>So importieren Sie Direct3D9-Inhalt  
  
1.  Öffnen Sie "MainWindow.Xaml.cs" im Code-Editor.  
  
2.  Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Hosten des Inhalts Direct3D9  
 Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage> Klasse zum Hosten des Direct3D9-Inhalts.  
  
#### <a name="to-host-the-direct3d9-content"></a>Zum Hosten des Inhalts Direct3D9  
  
1.  Ersetzen Sie in "MainWindow.xaml" den automatisch generierten XAML-Code durch Folgendes XAML.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Erstellen Sie das Projekt.  
  
3.  Kopieren Sie die DLL, die den Direct3D9-Inhalt in den Ordner "bin" / Debug enthält.  
  
4.  Drücken Sie F5, um das Projekt auszuführen.  
  
     Der Direct3D9-Inhalt in der WPF-Anwendung angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.D3DImage>  
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
