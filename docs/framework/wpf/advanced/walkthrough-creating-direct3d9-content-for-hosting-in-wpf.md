---
title: 'Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 321c4ba8659bd2226fff96e74e81ef24f0077c3d
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847333"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF
Diese exemplarische Vorgehensweise veranschaulicht die Erstellung von Direct3D9-Inhalt, der für das Hosten in einer Windows Presentation Foundation (WPF)-Anwendung geeignet ist. Weitere Informationen zum Hosten von Direct3D9-Inhalt in WPF-Anwendungen, finden Sie unter [zwischen WPF und Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).

 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:

-   Erstellen Sie ein Direct3D9-Projekt.

-   Konfigurieren des Direct3D9-Projekts für das Hosten in einer WPF-Anwendung.

 Wenn Sie fertig sind, müssen Sie eine DLL, die Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.

## <a name="prerequisites"></a>Vorraussetzungen
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

-   Visual Studio 2010.

-   DirectX SDK 9or später noch mal.

## <a name="creating-the-direct3d9-project"></a>Erstellen des Projekts Direct3D9
 Der erste Schritt ist zum Erstellen und konfigurieren Sie das Direct3D9-Projekt.

#### <a name="to-create-the-direct3d9-project"></a>Zum Erstellen des Projekts Direct3D9

1.  Erstellen Sie ein neues Win32-Projekt in C++, die mit dem Namen `D3DContent`.

     Die Win32-Anwendungsassistenten wird geöffnet und zeigt die Willkommensseite.

2.  Klicken Sie auf **Weiter**.

     Der Application Settings-Bildschirm angezeigt wird.

3.  In der **Anwendungstyp:** wählen Sie im Abschnitt der **DLL** Option.

4.  Klicken Sie auf **Fertig stellen**.

     Das Projekt D3DContent wird generiert.

5.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste in des D3DContent-Projekts, und wählen **Eigenschaften**.

     Die **D3DContent Eigenschaftenseiten** Dialogfeld wird geöffnet.

6.  Wählen Sie die **C/C++-** Knoten.

7.  In der **Additional Include Directories** geben der Speicherort des DirectX Ordner einschließen. Der Standardspeicherort für diesen Ordner ist: %ProgramFiles%\Microsoft DirectX SDK (*Version*) \include"-Unterverzeichnis.

8.  Doppelklicken Sie auf die **Linker** Knoten aus, um ihn zu erweitern.

9. In der **Zusätzliche Bibliotheksverzeichnisse** geben den Speicherort des Ordners der DirectX-Bibliotheken. Der Standardspeicherort für diesen Ordner ist: %ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.

10. Wählen Sie die **Eingabe** Knoten.

11. In der **zusätzliche Abhängigkeiten** fügen die `d3d9.lib` und `d3dx9.lib` Dateien.

12. Fügen Sie im Projektmappen-Explorer eine neue Moduldefinitionsdatei (.def) mit dem Namen `D3DContent.def` zum Projekt.

## <a name="creating-the-direct3d9-content"></a>Erstellen von Direct3D9-Inhalt
 Um die bestmögliche Leistung zu erhalten, muss Ihre Direct3D9-Inhalt bestimmte Einstellungen verwenden. Der folgende Code zeigt, wie Sie eine Direct3D9-Oberfläche zu erstellen, die beste Leistungsmerkmale aufweist. Weitere Informationen finden Sie unter [Leistungsüberlegungen hinsichtlich Direct3D9 und WPF-Interoperabilität](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>Die Direct3D9 Inhalte erstellen

1.  Projektmappen-Explorer das Projekt mit dem Namen im folgenden drei C++-Klassen hinzugefügt.

     `CRenderer` (mit virtuellen Destruktor)

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

9. Öffnen Sie dllmain.cpp im Code-Editor zu, und Ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. D3DContent.def im Code-Editor zu öffnen.

11. Ersetzen Sie den automatisch generierten Code durch den folgenden Code ein.

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

-   Hosten Sie den Direct3D9-Inhalt in einer WPF-Anwendung. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.D3DImage>
- [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)