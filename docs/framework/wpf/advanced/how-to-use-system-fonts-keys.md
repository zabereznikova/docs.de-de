---
title: 'Vorgehensweise: Verwenden von Systemschriftartschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 7283e4225b75909322fa312583e9f1a0679762e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918385"
---
# <a name="how-to-use-system-fonts-keys"></a>Vorgehensweise: Verwenden von Systemschriftartschlüsseln
Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemFonts>ist eine Klasse, die sowohl System Schriftart Werte als auch System Schriftart Ressourcen enthält, die an die Werte gebunden werden <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> , <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>z. –. und.  
  
 Systemschriftarteigenschaften können als statische oder dynamische Ressourcen verwendet werden. Verwenden Sie eine dynamische Ressource, wenn sich die Schriftarteigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
> Dynamischen Ressourcen wird der Schlüsselwort *Schlüssel* an den Eigenschaftsnamen angehängt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemschriftart zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. Dieses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel erstellt einen Schaltflächen Stil, <xref:System.Windows.SystemFonts> der einer Schaltfläche Werte zuweist.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Siehe auch

- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
- [Verwenden von SystemFonts](how-to-use-systemfonts.md)
