---
title: 'Vorgehensweise: Verwenden von SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 5976bc0cb8b34e68d5e89dd70a608d7e52ded332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216781"
---
# <a name="how-to-use-systemfonts"></a>Vorgehensweise: Verwenden von SystemFonts
Dieses Beispiel zeigt, wie Sie mit der statischen Ressourcen der der <xref:System.Windows.SystemFonts> Klasse zum Formatieren oder Anpassen einer Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts> ist eine Klasse, die enthält sowohl als statische Eigenschaften und Eigenschaften, die auf Ressourcenschlüssel verweisen, die verwendet werden können, um diese Werte dynamisch zur Laufzeit zugreifen. Z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ist eine <xref:System.Windows.SystemFonts> Wert und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemFonts> als statische Eigenschaften oder dynamische Ressourcenverweise (mit dem statischen Eigenschaftswert als Schlüssel). Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.  
  
> [!NOTE]
>  Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.  
  
 Das folgende Beispiel zeigt, wie Sie den Zugriff auf und verwenden Sie die Eigenschaften der <xref:System.Windows.SystemFonts> als statische Werte zum Formatieren oder Anpassen einer Schaltfläche. Dieses Markupbeispiel weist <xref:System.Windows.SystemFonts> Werte auf eine Schaltfläche.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Verwenden Sie die Werte der <xref:System.Windows.SystemFonts> in Code, Sie müssen keinen statischen Wert oder einen dynamischen Ressourcenverweis zu verwenden. Verwenden Sie stattdessen die Nichtschlüsseleigenschaften der der <xref:System.Windows.SystemFonts> Klasse. Obwohl die Nichtschlüsseleigenschaften scheinbar als statische Eigenschaften, die das Laufzeitverhalten des definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie von gehostet wird das System Systemwerten die Eigenschaften in Echtzeit und benutzergesteuerte Änderungen von ordnungsgemäß berücksichtigt wird. Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.SystemFonts>
- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
- [Verwenden von Systemschriftartschlüsseln](how-to-use-system-fonts-keys.md)
- [Gewusst wie-Themen](resources-how-to-topics.md)
- [x:Statische Markuperweiterung](../../xaml-services/x-static-markup-extension.md)
- [XAML-Ressourcen](xaml-resources.md)
- [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md)
