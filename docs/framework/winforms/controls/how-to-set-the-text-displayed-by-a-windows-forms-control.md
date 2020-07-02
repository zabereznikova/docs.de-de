---
title: Festlegen des von einem Steuerelement angezeigten Texts
description: Erfahren Sie, wie Sie den Text festlegen, der von einem Windows Forms Steuerelement angezeigt wird. Legen Sie den Text mithilfe der Text-Eigenschaft fest oder geben Sie ihn zurück, oder ändern Sie die Schriftart mithilfe der Font-Eigenschaft.
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 35bae5830bfee8ab91f7b6c7b9dcc6d6b8db00ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622847"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Gewusst wie: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts

Windows Forms Steuerelemente zeigen normalerweise Text an, der mit der primären Funktion des Steuer Elements verknüpft ist. Ein Steuerelement zeigt beispielsweise <xref:System.Windows.Forms.Button> in der Regel eine Beschriftung an, die angibt, welche Aktion ausgeführt wird, wenn auf die Schaltfläche geklickt wird. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.

Sie können den Text auch mit dem- [Designer](#designer)festlegen.

## <a name="programmatic"></a>Programmgesteuert

1. Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.

   Zum Erstellen einer unterstrichenen Zugriffstaste enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Zugriffstaste verwendet wird.

2. Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente. Mit der folgenden Codezeile wird z. b. der Text des Menü Elements so festgelegt, dass der Text "& jetzt für etwas unterschiedliches Element" lautet:

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a>Designer

1. Legen Sie im **Eigenschaften** Fenster von Visual Studio die **Text** -Eigenschaft des-Steuer Elements auf eine entsprechende Zeichenfolge fest.

   Zum Erstellen einer unterstrichenen Tastenkombination enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Tastenkombination verwendet werden soll.

2. Wählen Sie im Fenster **Eigenschaften** die Schaltfläche mit den Auslassungs Punkten (Auslassungs Zeichen ![ (...) im Eigenschaftenfenster von Visual Studio ](./media/visual-studio-ellipsis-button.png) ) neben der Eigenschaft **Schriftart** aus.

   Wählen Sie im Dialogfeld Standard Schriftart die Schriftart, den Schrift Schnitt, die Größe, die Effekte (z. b. durchgestrichen oder unterstreichen) und das gewünschte Skript aus.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
