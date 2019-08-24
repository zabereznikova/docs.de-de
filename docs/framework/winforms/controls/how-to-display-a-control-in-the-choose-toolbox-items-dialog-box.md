---
title: 'Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a6938b4fe651e13f3ec96642db6027143f1f028
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015892"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“

Wenn Sie Steuerelemente entwickeln und verteilen, möchten Sie möglicherweise, dass diese Steuerelemente im Dialogfeld **Toolbox Elemente auswählen** von Visual Studio angezeigt werden, das angezeigt wird, wenn Sie mit der rechten Maustaste auf die **Toolbox** klicken und **Elemente auswählen**auswählen. Sie können das Steuerelement in diesem Dialogfeld mithilfe der AssemblyFoldersEx-Registrierungs Prozedur anzeigen lassen.

So zeigen Sie das Steuerelement im Dialogfeld Toolbox Elemente auswählen an:

- Installieren Sie die steuerungsassembly im globalen Assemblycache. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)

  -oder-

- Registrieren Sie das Steuerelement und die zugehörigen Entwurfszeit-Assemblys mithilfe der AssemblyFoldersEx-Registrierungs Prozedur. AssemblyFoldersEx ist ein Registrierungs Speicherort, an dem Drittanbieter Pfade für jede Version des Frameworks speichern, das Sie unterstützen. Die Entwurfszeit Auflösung kann in diesem Registrierungs Speicherort nach Verweisassemblys suchen. Das Registrierungs Skript kann die Steuerelemente angeben, die in der Toolbox angezeigt werden sollen.

## <a name="see-also"></a>Siehe auch

- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
