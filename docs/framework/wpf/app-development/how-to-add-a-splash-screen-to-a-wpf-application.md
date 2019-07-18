---
title: 'Vorgehensweise: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 3120ee64d65822d323800a89466c6b707169aaaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947900"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Vorgehensweise: Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung

In diesem Thema wird gezeigt, wie einem Startfenster hinzufügen oder *Begrüßungsbildschirm*, an eine Windows Presentation Foundation (WPF)-Anwendung.

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>So fügen Sie ein vorhandenes Image als eines Begrüßungsbildschirms hinzu

1. Erstellen Sie oder suchen Sie ein Bild, das Sie für den Begrüßungsbildschirm verwenden möchten. Sie können jedes Bildformat verwenden, die von der Windows Imaging Component (WIC) unterstützt wird. Beispielsweise können Sie die BMP, GIF, JPEG, PNG und TIFF-Format verwenden.

2. Fügen Sie die Imagedatei dem Projekt WPF-Anwendung.

3. In **Projektmappen-Explorer**, wählen Sie das Image.

4. Klicken Sie im Eigenschaftenfenster auf die Dropdown-Pfeil für die **Buildvorgang** Eigenschaft.

5. Wählen Sie **SplashScreen** aus der Dropdown-Liste.

6. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

     Das Image des Begrüßungsbildschirms wird in der Mitte des Bildschirms, und klicken Sie dann ausgeblendet wird, wenn das Hauptanwendungsfenster angezeigt wird.

## <a name="to-exclude-the-splash-screen-from-build"></a>Den Begrüßungsbildschirm aus Build ausschließen

1. In **Projektmappen-Explorer**, wählen Sie das Image des Begrüßungsbildschirms.

2. In der **Eigenschaften** legen die **Buildvorgang** zu **keine**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>So entfernen Sie den Begrüßungsbildschirm von einer Anwendung

In **Projektmappen-Explorer**, löschen Sie das Image des Begrüßungsbildschirms.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.SplashScreen>
- [Vorgehensweise: Fügen Sie vorhandener Elemente zu einem Projekt hinzu](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
