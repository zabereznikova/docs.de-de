---
title: 'Vorgehensweise: Sperren von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 9eb762a9691a6127e2419f9ddc25f3010d3383fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966525"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Vorgehensweise: Sperren von Steuerelementen für Windows Forms
Wenn Sie die Benutzeroberfläche der Windows-Anwendung entwerfen, können Sie die Steuerelemente nach der ordnungsgemäßen Positionierung sperren, damit Sie Sie nicht versehentlich verschieben oder ändern, wenn Sie andere Eigenschaften festlegen.

 Darüber hinaus können Sie alle Steuerelemente im Formular auf einmal Sperren und entsperren, was für Formulare mit vielen Steuerelementen hilfreich ist, oder Sie können einzelne Steuerelemente entsperren. Nachdem Sie alle Steuerelemente auf dem Formular abgelegt haben, Sperren Sie Sie alle an Ort und Stelle, um eine fehlerhafte Bewegung zu verhindern.

## <a name="to-lock-a-control"></a>So sperren Sie ein Steuerelement

1. Klicken Sie im Fenster **Eigenschaften** auf die Eigenschaft **gesperrt** , und `true`wählen Sie aus. (Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)

     Klicken Sie alternativ mit der rechten Maustaste auf das Steuerelement, und wählen Sie Steuer **Elemente sperren**

    > [!NOTE]
    > Sperr Steuerelemente verhindern, dass Sie auf der Entwurfs Oberfläche an eine neue Größe oder Position gezogen werden. Sie können jedoch weiterhin die Größe oder Position von Steuerelementen mithilfe des **Eigenschaften** Fensters oder im Code ändern.

## <a name="to-lock-all-the-controls-on-a-form"></a>So sperren Sie alle Steuerelemente auf einem Formular

1. Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.

    > [!NOTE]
    > Dieser Befehl sperrt auch die Größe des Formulars, da ein Formular ein Steuerelement ist.

## <a name="to-unlock-all-locked-controls-on-a-form"></a>So entsperren Sie alle gesperrten Steuerelemente auf einem Formular

1. Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.

     Alle zuvor gesperrten Steuerelemente auf dem Formular sind nun entsperrt.

## <a name="to-unlock-locked-controls-individually"></a>So entsperren Sie gesperrte Steuerelemente einzeln

1. Klicken Sie im Fenster **Eigenschaften** auf die Eigenschaft **gesperrt** , und `false`wählen Sie aus. (Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
