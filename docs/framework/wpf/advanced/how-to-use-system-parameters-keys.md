---
title: 'Vorgehensweise: Verwenden von Systemparameterschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: 147f65b4bb214c12317309081c345251d7426cd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001441"
---
# <a name="how-to-use-system-parameters-keys"></a>Vorgehensweise: Verwenden von Systemparameterschlüsseln
Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemParameters> ist eine Klasse, die sowohl Systemparameterwerte und Ressourcenschlüssel, der an die Werte gebunden enthält – z. B. <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>. Systemparametereigenschaften können als statische oder dynamische Ressourcen verwendet werden. Verwenden Sie eine dynamische Ressource, wenn sich die Parametereigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
>  Dynamische Ressourcen haben das Schlüsselwort *Schlüssel* an den Eigenschaftennamen angefügt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemparamter zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel die Größe einer Schaltfläche durch Zuweisen von <xref:System.Windows.SystemParameters> Werte für Breite und Höhe der Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Siehe auch

- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemFonts](how-to-use-systemfonts.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
