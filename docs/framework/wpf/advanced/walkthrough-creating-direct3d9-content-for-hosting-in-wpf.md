---
title: "Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF | Microsoft Docs"
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
  - "Direct3D9 [WPF-Interoperabilität], Erstellen von Direct3D9-Inhalten"
  - "WPF, Erstellen von Direct3D9-Inhalten"
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie Direct3D9\-Inhalte zum Hosten in einer WPF\-Anwendung \(Windows Presentation Foundation\) erstellen.  Weitere Informationen zum Hosten von Direct3D9\-Inhalten in WPF\-Anwendungen finden Sie unter [Interaktion zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen Sie ein Direct3D9\-Projekt.  
  
-   Konfigurieren Sie das Direct3D9\-Projekt für das Hosting in einer WPF\-Anwendung.  
  
 Am Ende des Prozesses verfügen Sie über eine DLL, die Direct3D9\-Inhalte zur Verwendung in einer WPF\-Anwendung enthält.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 oder höher.  
  
## Erstellen des Direct3D9\-Projekts  
 Zunächst wird das Direct3D9\-Projekt erstellt und konfiguriert.  
  
#### So erstellen Sie das Direct3D9\-Projekt  
  
1.  Erstellen Sie in C\+\+ ein neues Win32\-Projekt mit dem Namen `D3DContent`.  
  
     Der Win32\-Anwendungs\-Assistent wird geöffnet und zeigt die Willkommensseite an.  
  
2.  Klicken Sie auf **Next**.  
  
     Der Bildschirm mit den Anwendungseinstellungen wird angezeigt.  
  
3.  Wählen Sie im Abschnitt **Anwendungstyp:** die Option **DLL**.  
  
4.  Klicken Sie auf **Fertig stellen**.  
  
     Das D3DContent\-Projekt wird generiert.  
  
5.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf das D3DContent\-Projekt, und wählen Sie **Eigenschaften** aus.  
  
     Das Dialogfeld **D3DContent\-Eigenschaftenseiten** wird geöffnet.  
  
6.  Wählen Sie den Knoten **C\/C\+\+** aus.  
  
7.  Geben Sie im Feld **Zusätzliche Includeverzeichnisse** den Speicherort des DirectX\-Includeordners an.  Der Standardspeicherort für diesen Ordner ist %ProgramFiles%\\Microsoft DirectX SDK \(*Version*\)\\Include.  
  
8.  Doppelklicken Sie auf den Knoten **Linker**, um ihn zu erweitern.  
  
9. Geben Sie im Feld **Zusätzliche Bibliotheksverzeichnisse** den Speicherort des DirectX\-Bibliotheksordners an.  Der Standardspeicherort für diesen Ordner ist %ProgramFiles%\\Microsoft DirectX SDK \(*Version*\)\\Lib\\x86..  
  
10. Wählen Sie den Knoten **Input** aus.  
  
11. Fügen Sie im Feld **Zusätzliche Abhängigkeiten** die Dateien `d3d9.lib` und `d3dx9.lib` hinzu.  
  
12. Fügen Sie im Projektmappen\-Explorer dem Projekt mit dem Namen `D3DContent.def` eine neue Moduldefinitionsdatei \(.def\) hinzu.  
  
## Erstellen des Direct3D9\-Inhalts  
 Um die optimale Leistung zu erhalten, muss der Direct3D9\-Inhalt besondere Einstellungen verwenden.  Im folgenden Code wird gezeigt, wie eine Direct3D9\-Oberfläche mit optimalen Leistungseigenschaften erstellt wird.  Weitere Informationen hierzu finden Sie unter [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### So erstellen Sie den Direct3D9\-Inhalt  
  
1.  Fügen Sie mit dem Projektmappen\-Explorer drei C\+\+\-Klassen zu folgendem Projekt hinzu.  
  
     `CRenderer` \(mit virtuellem Destruktor\)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  Öffnen Sie Renderer.h im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  Öffnen Sie Renderer.cpp im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  Öffnen Sie RendererManager.h im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  Öffnen Sie RendererManager.cpp im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  Öffnen Sie TriangleRenderer.h im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  Öffnen Sie TriangleRenderer.cpp im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  Öffnen Sie stdafx.h im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. Öffnen Sie dllmain.cpp im Code\-Editor und ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. Öffnen Sie die Datei D3DContent.def im Code\-Editor.  
  
11. Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
    ```  
  
    LIBRARY "D3DContent"  
  
    EXPORTS  
  
    SetSize  
    SetAlpha  
    SetNumDesiredSamples  
    SetAdapter  
  
    GetBackBufferNoRef  
    Render  
    Destroy  
  
    ```  
  
12. Erstellen Sie das Projekt.  
  
## Nächste Schritte  
  
-   Hosten Sie den Direct3D9\-Inhalt in einer WPF\-Anwendung.  Weitere Informationen hierzu finden Sie unter [Exemplarische Vorgehensweise: Hosten von Direct3D9\-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## Siehe auch  
 <xref:System.Windows.Interop.D3DImage>   
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Exemplarische Vorgehensweise: Hosten von Direct3D9\-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)