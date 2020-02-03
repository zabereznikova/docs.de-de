---
title: Von Direct3D9-Inhalt für Hosting Erstellen
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 847ee74da5b295c2c9d3824b3df74f94bc98a4db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727920"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF
In dieser exemplarischen Vorgehensweise wird gezeigt, wie von Direct3D9-Inhalte erstellt werden, die sich für das Hosting in einer Windows Presentation Foundation (WPF)-Anwendung eignen. Weitere Informationen zum Hosting von von Direct3D9-Inhalten in WPF-Anwendungen finden Sie unter [WPF und von Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).

 In dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:

- Erstellen Sie ein von Direct3D9-Projekt.

- Konfigurieren Sie das von Direct3D9-Projekt für das Hosting in einer WPF-Anwendung.

 Wenn Sie fertig sind, verfügen Sie über eine DLL, die von Direct3D9-Inhalt für die Verwendung in einer WPF-Anwendung enthält.

## <a name="prerequisites"></a>Voraussetzungen
 Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Visual Studio 2010.

- DirectX SDK 9 oder höher.

## <a name="creating-the-direct3d9-project"></a>Erstellen des von Direct3D9-Projekts
 Der erste Schritt besteht darin, das von Direct3D9-Projekt zu erstellen und zu konfigurieren.

#### <a name="to-create-the-direct3d9-project"></a>So erstellen Sie das von Direct3D9-Projekt

1. Erstellen Sie ein neues Win32- C++ Projekt in mit dem Namen `D3DContent`.

     Der Win32-Anwendungs-Assistent wird geöffnet und zeigt den Willkommensbildschirm an.

2. Klicken Sie auf **Weiter**.

     Der Bildschirm "Anwendungseinstellungen" wird angezeigt.

3. Wählen Sie im Abschnitt **Anwendungstyp:** die **dll** -Option aus.

4. Klicken Sie auf **Fertig stellen**.

     Das D3DContent-Projekt wird generiert.

5. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt D3DContent, und wählen Sie **Eigenschaften**aus.

     Das Dialogfeld **D3DContent-Eigenschaften Seiten** wird geöffnet.

6. Wählen Sie den Knoten **C/C++**  aus.

7. Geben Sie im Feld **weitere Includeverzeichnisse** den Speicherort des DirectX Include-Ordners an. Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Include.

8. Doppelklicken Sie auf den **Linker** -Knoten, um ihn zu erweitern.

9. Geben Sie im Feld " **zusätzliche Bibliotheks Verzeichnisse** " den Speicherort des Ordners "DirectX-Bibliotheken" an. Der Standard Speicherort für diesen Ordner ist%ProgramFiles%\Microsoft DirectX SDK (*Version*) \Lib\x86.

10. Wählen Sie den **Eingabe** Knoten aus.

11. Fügen Sie im Feld **Zusätzliche Abhängigkeiten** die Dateien `d3d9.lib` und `d3dx9.lib` hinzu.

12. Fügen Sie in Projektmappen-Explorer dem Projekt eine neue Modul Definitionsdatei (. def) mit dem Namen `D3DContent.def` hinzu.

## <a name="creating-the-direct3d9-content"></a>Erstellen des von Direct3D9-Inhalts
 Um die bestmögliche Leistung zu erzielen, müssen ihre von Direct3D9-Inhalte bestimmte Einstellungen verwenden. Der folgende Code zeigt, wie eine von Direct3D9-Oberfläche erstellt wird, die die besten Leistungsmerkmale aufweist. Weitere Informationen finden Sie unter [Überlegungen zur Leistung bei der von Direct3D9-und WPF-Interoperabilität](performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>So erstellen Sie den von Direct3D9-Inhalt

1. Fügen Sie mit Projektmappen-Explorer dem C++ Projekt drei Klassen mit dem Namen hinzu.

     `CRenderer` (mit virtuellem Dekonstruktor)

     `CRendererManager`

     `CTriangleRenderer`

2. Öffnen Sie Renderer. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. Öffnen Sie "Renderer. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. Öffnen Sie RendererManager. h im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. Öffnen Sie "RendererManager. cpp" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. Öffnen Sie im Code-Editor die Datei "" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. Öffnen Sie "stdafx. h" im Code-Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. Öffnen Sie im Code-Editor die Datei "DllMain. cpp", und ersetzen Sie den automatisch generierten Code durch den folgenden Code.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. Öffnen Sie D3DContent. def im Code-Editor.

11. Ersetzen Sie den automatisch generierten Code durch den folgenden Code.

    ```cpp
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

- Hosten Sie den von Direct3D9-Inhalt in einer WPF-Anwendung. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Hosting von Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Interop.D3DImage>
- [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
