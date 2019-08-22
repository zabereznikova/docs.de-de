---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes'
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
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666156"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Vorgehensweise: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts

Windows Forms Steuerelemente zeigen normalerweise Text an, der mit der primären Funktion des Steuer Elements verknüpft ist. Ein <xref:System.Windows.Forms.Button> Steuerelement zeigt beispielsweise in der Regel eine Beschriftung an, die angibt, welche Aktion ausgeführt wird, wenn auf die Schaltfläche geklickt wird. Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben. Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.

Sie können den Text auch mit dem- [Designer](#designer)festlegen.

## <a name="programmatic"></a>Programmgesteuerten

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

2. Wählen Sie im Fenster **Eigenschaften** die Schaltfläche mit den Auslassungs Punkten (![Auslassungs Zeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der Eigenschaft **Schriftart** aus.

   Wählen Sie im Dialogfeld Standard Schriftart die Schriftart, den Schrift Schnitt, die Größe, die Effekte (z. b. durchgestrichen oder unterstreichen) und das gewünschte Skript aus.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Vorgehensweise: Erstellen von Zugriffs Schlüsseln für Windows Forms Steuerelemente](how-to-create-access-keys-for-windows-forms-controls.md)
- [Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks](how-to-respond-to-windows-forms-button-clicks.md)
