---
title: 'Vorgehensweise: Verwenden von Systemschriftartschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: e924f4c14d98380d9f4c0defe27d9f98c3293114
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001610"
---
# <a name="how-to-use-system-fonts-keys"></a>Vorgehensweise: Verwenden von Systemschriftartschlüsseln
Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts> eine Klasse, enthält sowohl Systemschriftartwerte und Systemschriftartressourcen, die an die Werte gebunden, ist – z. B. <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> und <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden. Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
>  Dynamische Ressourcen haben das Schlüsselwort *Schlüssel* an den Eigenschaftennamen angefügt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt eine Schaltflächen-Formatvorlage, die weist <xref:System.Windows.SystemFonts> Werte auf eine Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Siehe auch

- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
- [Verwenden von SystemFonts](how-to-use-systemfonts.md)
