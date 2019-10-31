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
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197464"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Verwenden von WPF-Steuerelementen in Windows Forms-apps

Sie können Windows Presentation Foundation (WPF)-Steuerelemente in Windows Forms-basierten Anwendungen verwenden. Obwohl es sich um zwei verschiedene Ansichts Technologien handelt, funktionieren Sie problemlos.

Der Windows Forms-Designer in Visual Studio stellt eine visuelle Entwurfs Umgebung zum Hosting von Windows Presentation Foundation Steuerelementen bereit. Ein WPF-Steuerelement wird von einem speziellen Windows Forms-Steuerelement gehostet, das <xref:System.Windows.Forms.Integration.ElementHost>heißt. Mit diesem Steuerelement kann das WPF-Steuerelement am Layout des Formulars teilnehmen und Tastatur-und Maus Meldungen empfangen. Zur Entwurfszeit können Sie das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement genauso wie jedes beliebige Windows Forms Steuerelement anordnen.

Sie können auch Windows Forms-Steuerelemente in WPF-basierten Anwendungen verwenden. Weitere Informationen finden Sie unter [Entwerfen von XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Siehe auch

- [WPF-und Windows Forms Interoperation](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
