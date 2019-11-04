---
title: 'Gewusst wie: Sperren von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d157ddc8be4b5fa0057241b562e76b566e8dad99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458342"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Gewusst wie: Sperren von Steuerelementen auf Windows Forms

Wenn Sie die Benutzeroberfläche der Windows-Anwendung entwerfen, können Sie die Steuerelemente nach der ordnungsgemäßen Positionierung sperren, damit Sie Sie nicht versehentlich verschieben oder ändern, wenn Sie andere Eigenschaften festlegen.

Darüber hinaus können Sie alle Steuerelemente im Formular auf einmal Sperren und entsperren, was für Formulare mit vielen Steuerelementen hilfreich ist, oder Sie können einzelne Steuerelemente entsperren. Nachdem Sie alle Steuerelemente auf dem Formular abgelegt haben, Sperren Sie Sie alle an Ort und Stelle, um eine fehlerhafte Bewegung zu verhindern.

## <a name="to-lock-a-control"></a>So sperren Sie ein Steuerelement

Wählen Sie im **Eigenschaften** Fenster von Visual Studio die Eigenschaft **gesperrt** aus, und wählen Sie dann **true**aus. (Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)

Klicken Sie alternativ mit der rechten Maustaste auf das Steuerelement, und wählen Sie Steuer **Elemente sperren**

> [!NOTE]
> Sperr Steuerelemente verhindern, dass Sie auf der Entwurfs Oberfläche an eine neue Größe oder Position gezogen werden. Sie können jedoch weiterhin die Größe oder Position von Steuerelementen mithilfe des **Eigenschaften** Fensters oder im Code ändern.

## <a name="to-lock-all-the-controls-on-a-form"></a>So sperren Sie alle Steuerelemente auf einem Formular

Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.

> [!NOTE]
> Dieser Befehl sperrt auch die Größe des Formulars, da ein Formular ein Steuerelement ist.

## <a name="to-unlock-all-locked-controls-on-a-form"></a>So entsperren Sie alle gesperrten Steuerelemente auf einem Formular

Wählen Sie im Menü **Format** die Option Steuer **Elemente sperren**aus.

Alle zuvor gesperrten Steuerelemente auf dem Formular sind nun entsperrt.

## <a name="to-unlock-locked-controls-individually"></a>So entsperren Sie gesperrte Steuerelemente einzeln

Wählen Sie im Fenster **Eigenschaften** die Eigenschaft **gesperrt** aus, und wählen Sie dann **false**aus. (Doppelklicken Sie auf den Namen, um die Eigenschafts Einstellung zu wechseln.)

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
