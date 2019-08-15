---
title: Auswirkungen beim Ändern der Darstellung von Basisformularen
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 5239017eb63ca6360ae8811a76497256fafbd1b1
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040133"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a>Auswirkungen der Änderung der Darstellung eines Basis Formulars

Während der Anwendungsentwicklung müssen Sie möglicherweise häufig die Darstellung des Basisformulars ändern, dessen Merkmale an andere Formulare im Projekt (oder in anderen Projekten) vererbt werden.

Zur Entwurfszeit werden Änderungen an der Darstellung des Basisformulars (z.B. das Festlegen von Eigenschaften oder die Addition und Subtraktion von Steuerelementen) in geerbten Formularen reflektiert, wenn das Projekt mit dem Basisformular erstellt wird. Es genügt nicht, wenn Sie die am Basisformular vorgenommenen Änderungen einfach speichern. Wählen Sie aus dem Menü **Erstellen** die Option **Erstellen** aus, um ein Projekt zu erstellen.

Änderungen, die zur Laufzeit am Basisformular vorgenommen werden, haben keine Auswirkungen auf geerbte Formulare, die bereits instanziiert werden.

## <a name="see-also"></a>Siehe auch

- [base](~/docs/csharp/language-reference/keywords/base.md)
- [Vorgehensweise: Windows Forms erben](how-to-inherit-windows-forms.md)
- [Visuelle Vererbung in Windows Forms](windows-forms-visual-inheritance.md)
