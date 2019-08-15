---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039522"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers
Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs, Menü Elements oder der Bezeichnung eines Steuer Elements, z. b. einer Schaltfläche. Dadurch kann der Benutzer auf eine Schaltfläche klicken, indem er die Alt-Taste in Kombination mit der vordefinierten Zugriffstaste drückt. Wenn z. b. eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und die `Text` -Eigenschaft daher auf "Print" festgelegt ist, wird durch das Hinzufügen eines kaufmännischen und-Zeichens (&) vor dem Buchstaben "p" der Buchstabe "p" im Schaltflächen Text zur Laufzeit unterstrichen. Der Benutzer kann den Befehl ausführen, der der Schaltfläche zugeordnet ist, indem er alt + P drückt. Sie können keinen Zugriffsschlüssel für ein Steuerelement haben, das keinen Fokus erhalten kann.

## <a name="to-create-an-access-key-for-a-control"></a>So erstellen Sie einen Zugriffsschlüssel für ein Steuerelement

1. Legen Sie im Fenster **Eigenschaften** die `Text` -Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben enthält, der als Zugriffstaste verwendet wird. Wenn Sie z. b. den Buchstaben "P" als Zugriffsschlüssel festlegen möchten, geben Sie **& Drucken** im Raster ein.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Button>
- [Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks](how-to-respond-to-windows-forms-button-clicks.md)
- [Vorgehensweise: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
