---
title: 'Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 750e5c42158a87c04a7fb0f2a83f126a698bb93f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF
In dieser exemplarischen Vorgehensweise veranschaulicht die Direct3D9 Inhalte zu erstellen, die für das hosting in einer Windows Presentation Foundation (WPF)-Anwendung geeignet ist. Weitere Informationen zum Hosten von Direct3D9-Inhalt in WPF-Anwendungen finden Sie unter [WPF und Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen Sie ein Direct3D9-Projekt.  
  
-   Konfigurieren Sie das Direct3D9-Projekt für das hosting in einer WPF-Anwendung.  
  
 Wenn Sie fertig sind, müssen Sie eine DLL, die Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9or später erneut.  
  
## <a name="creating-the-direct3d9-project"></a>Erstellen des Projekts Direct3D9  
 Der erste Schritt ist zum Erstellen und konfigurieren Sie das Direct3D9-Projekt.  
  
#### <a name="to-create-the-direct3d9-project"></a>Zum Erstellen des Projekts Direct3D9  
  
1.  Erstellen Sie ein neues Win32-Projekt in C++ mit dem Namen `D3DContent`.  
  
     Die Win32-Anwendung-Assistent wird geöffnet und zeigt die Willkommenseite.  
  
2.  Klicken Sie auf **Weiter**.  
  
     Die Anwendungseinstellungen-Bildschirm wird angezeigt.  
  
3.  In der **Anwendungstyp:** Abschnitt der **DLL** Option.  
  
4.  Klicken Sie auf **Fertig stellen**.  
  
     Das D3DContent-Projekt wird generiert.  
  
5.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste des D3DContent-Projekts, und wählen **Eigenschaften**.  
  
     Die **D3DContent Eigenschaftenseiten** Dialogfeld wird geöffnet.  
  
6.  Wählen Sie die **C/C++-** Knoten.  
  
7.  In der **Zusätzliche Includeverzeichnisse** Feld, geben Sie der Speicherort des DirectX Ordner einschließen. Der Standardspeicherort für diesen Ordner ist %ProgramFiles%\Microsoft DirectX SDK (*Version*) \include"-Unterverzeichnis.  
  
8.  Doppelklicken Sie auf die **Linker** Knoten, um ihn zu erweitern.  
  
9. In der **Zusätzliche Bibliotheksverzeichnisse** Feld, geben Sie den Speicherort des Ordners, DirectX-Bibliotheken. Der Standardspeicherort für diesen Ordner ist %ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.  
  
10. Wählen Sie die **Eingabe** Knoten.  
  
11. In der **zusätzliche Abhängigkeiten** Feld, fügen Sie der `d3d9.lib` und `d3dx9.lib` Dateien.  
  
12. Fügen Sie im Projektmappen-Explorer eine neue Moduldefinitionsdatei (.def) mit dem Namen `D3DContent.def` zum Projekt.  
  
## <a name="creating-the-direct3d9-content"></a>Erstellen den Direct3D9-Inhalt  
 Um die optimale Leistung zu erhalten, muss Ihre Inhalte Direct3D9 bestimmte Einstellungen verwenden. Der folgende Code zeigt, wie eine Direct3D9-Oberfläche erstellen, die die beste Leistungsmerkmale aufweist. Weitere Informationen finden Sie unter [Überlegungen zur Leistung für WPF-Interoperabilität und Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### <a name="to-create-the-direct3d9-content"></a>Erstellen des Inhalts der Direct3D9 für  
  
1.  Fügen Sie drei C++-Klassen mithilfe Projektmappen-Explorer auf das Projekt mit dem Namen Folgendes aus.  
  
     `CRenderer`(mit virtuellen Destruktor)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  Öffnen Sie Renderer.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  Öffnen Sie Renderer.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  Öffnen Sie RendererManager.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  Öffnen Sie RendererManager.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  Öffnen Sie TriangleRenderer.h im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  Öffnen Sie TriangleRenderer.cpp im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  Öffnen Sie "stdafx.h" im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. Öffnen Sie "DllMain.cpp" im Code-Editor, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. D3DContent.def im Code-Editor zu öffnen.  
  
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
  
## <a name="next-steps"></a>Nächste Schritte  
  
-   Hosten Sie die Direct3D9-Inhalt in einer WPF-Anwendung. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Direct3D9 Content in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.D3DImage>  
 [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
