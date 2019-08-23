---
title: 'Vorgehensweise: Verwenden von Systemparameterschlüsseln'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918371"
---
# <a name="how-to-use-system-parameters-keys"></a>Vorgehensweise: Verwenden von Systemparameterschlüsseln
Systemressourcen machen eine Reihe von Systemmetriken als Ressourcen verfügbar, damit Entwickler visuelle Elemente erstellen können, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemParameters>ist eine Klasse, die sowohl Systemparameter Werte als auch Ressourcen Schlüssel enthält, die an die Werte gebunden werden <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> , <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>z. –. und. Systemparametereigenschaften können als statische oder dynamische Ressourcen verwendet werden. Verwenden Sie eine dynamische Ressource, wenn sich die Parametereigenschaft während der Ausführung der Anwendung aktualisieren soll; verwenden Sie andernfalls eine statische Ressource.  
  
> [!NOTE]
> Dynamischen Ressourcen wird der Schlüsselwort *Schlüssel* an den Eigenschaftsnamen angehängt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie auf dynamische Ressourcen der Systemparamter zugreifen und diese verwenden, um eine Schaltfläche zu formatieren oder anzupassen. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] diesem Beispiel wird eine Schaltfläche <xref:System.Windows.SystemParameters> durch Zuweisen von Werten zur Breite und Höhe der Schaltfläche unterschiedlich dargestellt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Siehe auch

- [Zeichnen eines Bereichs mit einem Systempinsel](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemFonts](how-to-use-systemfonts.md)
- [Verwenden von SystemParameters](how-to-use-systemparameters.md)
