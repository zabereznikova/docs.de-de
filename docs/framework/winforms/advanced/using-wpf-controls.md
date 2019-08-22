---
title: Verwenden von WPF-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5ea92b24a2ca30c0ad137d83c8f521a952ad0c6b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658497"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Verwenden von WPF-Steuerelementen in Windows Forms-apps

Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden. Obwohl es sich um zwei verschiedene Ansichts Technologien handelt, funktionieren Sie problemlos.

Der Windows Forms-Designer in Visual Studio stellt eine visuelle Entwurfs Umgebung zum Hosting von Windows Presentation Foundation Steuerelementen bereit. Ein WPF-Steuerelement wird von einem speziellen Windows Forms Steuerelement mit <xref:System.Windows.Forms.Integration.ElementHost>dem Namen gehostet. Mit diesem Steuerelement kann das WPF-Steuerelement am Layout des Formulars teilnehmen und Tastatur-und Maus Meldungen empfangen. Zur Entwurfszeit können Sie das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement genauso anordnen wie alle Windows Forms Steuerelemente.

Sie können auch Windows Forms-Steuerelemente in WPF-basierten Anwendungen verwenden. Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Siehe auch

- [WPF-und Windows Forms Interoperation](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
