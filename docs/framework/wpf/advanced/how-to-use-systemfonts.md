---
title: 'Gewusst wie: Verwenden von SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 63ba7a6fb1c8776cc35c0e6f07a6b78f5b3d93d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459509"
---
# <a name="how-to-use-systemfonts"></a>Gewusst wie: Verwenden von SystemFonts
In diesem Beispiel wird gezeigt, wie die statischen Ressourcen der <xref:System.Windows.SystemFonts>-Klasse verwendet werden, um eine Schaltfläche zu formatieren oder anzupassen.  
  
## <a name="example"></a>Beispiel  
 Systemressourcen machen mehrere vom System festgelegte Werte als Ressourcen und Eigenschaften verfügbar, um visuelle Elemente zu erstellen, mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts> ist eine Klasse, die sowohl System Schriftart Werte als statische Eigenschaften als auch Eigenschaften enthält, die auf Ressourcen Schlüssel verweisen, die für den dynamischen Zugriff auf diese Werte zur Laufzeit verwendet werden können. Beispielsweise ist <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> ein <xref:System.Windows.SystemFonts> Wert, und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> ist ein entsprechender Ressourcen Schlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie die Member von <xref:System.Windows.SystemFonts> entweder als statische Eigenschaften oder als dynamische Ressourcen Verweise (mit dem statischen Eigenschafts Wert als Schlüssel) verwenden. Verwenden Sie einen dynamischen Ressourcenverweis, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung automatisch aktualisieren soll; verwenden Sie andernfalls einen statischen Wertverweis.  
  
> [!NOTE]
> Die Ressourcenschlüssel verfügen über das Suffix „Key“, das an den Eigenschaftennamen angefügt wird.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie auf die Eigenschaften von <xref:System.Windows.SystemFonts> als statische Werte zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. In diesem Markup Beispiel werden einer Schaltfläche <xref:System.Windows.SystemFonts> Werte zugewiesen.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Wenn Sie die Werte von <xref:System.Windows.SystemFonts> im Code verwenden möchten, müssen Sie weder einen statischen Wert noch einen dynamischen Ressourcen Verweis verwenden. Verwenden Sie stattdessen die nicht Schlüsseleigenschaften der <xref:System.Windows.SystemFonts>-Klasse. Obwohl die nicht Schlüsseleigenschaften scheinbar als statische Eigenschaften definiert sind, wertet das Laufzeitverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], wie vom System gehostet, die Eigenschaften in Echtzeit neu aus und berücksichtigt benutzergesteuerte Änderungen an System Werten ordnungsgemäß. Im folgenden Beispiel wird veranschaulicht, wie die Schriftarteinstellung einer Schaltfläche festgelegt wird.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.SystemFonts>
- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
- [Verwenden von Systemschriftartschlüsseln](how-to-use-system-fonts-keys.md)
- [Themen zu Vorgehensweisen](resources-how-to-topics.md)
- [x:Statische Markuperweiterung](../../xaml-services/x-static-markup-extension.md)
- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md)
