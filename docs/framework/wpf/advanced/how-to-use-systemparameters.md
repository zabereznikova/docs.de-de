---
title: 'Vorgehensweise: Verwenden von SystemParameters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 00afc5c12ea9b83759361e9a3f175e91b4cbb10d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541663"
---
# <a name="how-to-use-systemparameters"></a>Vorgehensweise: Verwenden von SystemParameters
Dieses Beispiel zeigt, wie Sie den Zugriff auf und verwenden Sie die Eigenschaften der <xref:System.Windows.SystemParameters> zum Formatieren oder Anpassen einer Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 Systemressourcen machen mehrere systembasierte Einstellungen als Ressourcen verfügbar, um visuelle Elemente zu erstellen, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemParameters> ist eine Klasse, die enthält sowohl Systemparameter und Ressourcenschlüssel, der an die Werte gebunden. Z. B. <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ist eine <xref:System.Windows.SystemParameters> Eigenschaftswert und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> ist der dazugehörige Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemParameters> als statische Eigenschaft oder eine dynamische Ressourcenverweise (mit dem statischen Eigenschaftswert als Schlüssel). Verwenden Sie einen dynamischen Ressourcenverweis, wenn der systembasierte Wert automatisch beim Ausführen der Anwendung aktualisiert werden soll; verwenden Sie andernfalls einen statischen Verweis. Ressourcenschlüssel verfügen über das Suffix `Key` an den Eigenschaftennamen angefügt.  
  
 Das folgende Beispiel zeigt, wie Sie den Zugriff auf und verwenden Sie die statische Werte von <xref:System.Windows.SystemParameters> zu formatieren oder Anpassen einer Schaltfläche. In diesem Markupbeispiel wird die Größe einer Schaltfläche durch Anwenden von <xref:System.Windows.SystemParameters> Werte auf eine Schaltfläche.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Verwenden Sie die Werte der <xref:System.Windows.SystemParameters> in Code, Sie müssen keine statischen Verweise oder dynamischen Ressourcenverweise verwenden. Verwenden Sie stattdessen die Werte der <xref:System.Windows.SystemParameters> Klasse. Obwohl die Nichtschlüsseleigenschaften scheinbar als statische Eigenschaften, die das Laufzeitverhalten des definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie vom System gehostet wird, erneut auswerten, die Eigenschaften in Echtzeit und wird ordnungsgemäß Konto für benutzergesteuerte Änderungen von. Das folgende Beispiel zeigt, wie Sie die Breite und Höhe einer Schaltfläche mithilfe von festlegen <xref:System.Windows.SystemParameters> Werte.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.SystemParameters>
- [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
- [Verwenden von Systemparameterschlüsseln](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
