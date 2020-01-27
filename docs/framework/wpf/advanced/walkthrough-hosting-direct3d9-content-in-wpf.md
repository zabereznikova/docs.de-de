---
title: Host von Direct3D9 Inhalt in WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: e65b0c59268b44abed289e54181bf0bda9355664
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742603"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF

In dieser exemplarischen Vorgehensweise wird das Hosten von von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung veranschaulicht.

Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:

- Erstellen Sie ein WPF-Projekt zum Hosten des von Direct3D9-Inhalts.

- Importieren Sie den von Direct3D9-Inhalt.

- Zeigen Sie den von Direct3D9-Inhalt mit der <xref:System.Windows.Interop.D3DImage>-Klasse an.

 Wenn Sie fertig sind, wissen Sie, wie Sie von Direct3D9-Inhalte in einer WPF-Anwendung hosten.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio erstellen.

- DirectX SDK 9 oder höher.

- Eine DLL, die von Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält. Weitere Informationen finden Sie unter [WPF und von Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) und Exemplarische Vorgehensweise [: Erstellen von von Direct3D9-Inhalten für das Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).

## <a name="creating-the-wpf-project"></a>Erstellen des WPF-Projekts

Der erste Schritt besteht darin, das Projekt für die WPF-Anwendung zu erstellen.

### <a name="to-create-the-wpf-project"></a>So erstellen Sie das WPF-Projekt

Erstellen Sie ein neues WPF-Anwendungsprojekt C# in Visual namens `D3DHost`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

Die Datei "MainWindow. XAML" wird im WPF-Designer geöffnet.

## <a name="importing-the-direct3d9-content"></a>Importieren des von Direct3D9-Inhalts

Mit dem `DllImport`-Attribut importieren Sie den von Direct3D9-Inhalt aus einer nicht verwalteten DLL.

### <a name="to-import-direct3d9-content"></a>So importieren Sie von Direct3D9-Inhalt

1. Öffnen Sie MainWindow.XAML.cs im Code-Editor.

2. Ersetzen Sie den automatisch generierten Code durch den folgenden Code.

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>Hosting des von Direct3D9-Inhalts

Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage>-Klasse, um den von Direct3D9-Inhalt zu hosten.

### <a name="to-host-the-direct3d9-content"></a>So hosten Sie den von Direct3D9-Inhalt

1. Ersetzen Sie in "MainWindow. XAML" den automatisch generierten XAML-Code durch den folgenden XAML-Code.

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. Erstellen Sie das Projekt.

3. Kopieren Sie die dll, die den von Direct3D9-Inhalt enthält, in den Ordner bin/Debug.

4. Drücken Sie F5, um das Projekt auszuführen.

    Der von Direct3D9-Inhalt wird in der WPF-Anwendung angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.D3DImage>
- [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
