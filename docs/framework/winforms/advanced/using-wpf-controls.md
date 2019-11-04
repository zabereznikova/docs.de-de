---
title: Verwenden von WPF-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460696"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Verwenden von WPF-Steuerelementen in Windows Forms-apps

Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden. Obwohl es sich um zwei verschiedene Ansichts Technologien handelt, funktionieren Sie problemlos.

Der Windows Forms-Designer in Visual Studio stellt eine visuelle Entwurfs Umgebung zum Hosting von Windows Presentation Foundation Steuerelementen bereit. Ein WPF-Steuerelement wird von einem speziellen Windows Forms-Steuerelement gehostet, das <xref:System.Windows.Forms.Integration.ElementHost>heißt. Mit diesem Steuerelement kann das WPF-Steuerelement am Layout des Formulars teilnehmen und Tastatur-und Maus Meldungen empfangen. Zur Entwurfszeit können Sie das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement genauso wie jedes beliebige Windows Forms Steuerelement anordnen.

Sie können auch Windows Forms-Steuerelemente in WPF-basierten Anwendungen verwenden. Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Siehe auch

- [WPF-und Windows Forms Interoperation](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
