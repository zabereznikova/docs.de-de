---
title: Erstellen von Zugriffs Schlüsseln für Steuerelemente
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731172"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Gewusst wie: Erstellen von Zugriffs Schlüsseln für Windows Forms Steuerelemente

Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs, Menü Elements oder der Bezeichnung eines Steuer Elements, z. b. einer Schaltfläche. Mit einer Zugriffstaste kann der Benutzer auf eine Schaltfläche klicken, indem er die Alt-Taste in Kombination mit der vordefinierten Zugriffstaste drückt. Wenn z. b. eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und deren `Text`-Eigenschaft auf "Drucken" festgelegt ist, wird durch das Hinzufügen eines kaufmännisches und vor dem Buchstaben "p" der Buchstabe "p" im Schaltflächen Text zur Laufzeit unterstrichen. Der Benutzer kann den Befehl ausführen, der der Schaltfläche zugeordnet ist, indem er alt + P drückt.

Steuerelemente, die keinen Fokus erhalten können, dürfen keine Zugriffsschlüssel aufweisen.

## <a name="programmatic"></a>Programmgesteuert

Legen Sie die `Text`-Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben enthält, der als Verknüpfung verwendet wird.

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> Wenn Sie ein kaufmännisches und in einer Beschriftung verwenden möchten, ohne einen Zugriffsschlüssel zu erstellen, schließen Sie zwei kaufmännische (& &) ein. Ein kaufmännisches und-Zeichen wird in der Beschriftung angezeigt, und es werden keine Zeichen unterstrichen.

## <a name="designer"></a>Designer

Legen Sie im **Eigenschaften** Fenster von Visual Studio die **Text** -Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen ("&") vor dem Buchstaben enthält, der als Zugriffstaste verwendet wird. Wenn Sie z. b. den Buchstaben "P" als Zugriffsschlüssel festlegen möchten, geben Sie **& Print**ein.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Button>
- [Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
