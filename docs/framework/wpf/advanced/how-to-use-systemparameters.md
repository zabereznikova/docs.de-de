---
title: 'Gewusst wie: Verwenden von SystemParameters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 07b73d78a022e508f9ed8ca2e80b71bc2ab89910
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-systemparameters"></a>Gewusst wie: Verwenden von SystemParameters
In diesem Beispiel wird gezeigt, wie zugreifen auf und verwenden die Eigenschaften des <xref:System.Windows.SystemParameters> um formatieren oder Anpassen einer Schaltfläche.  
  
## <a name="example"></a>Beispiel  
 Systemressourcen machen mehrere systembasierte Einstellungen als Ressourcen verfügbar, um visuelle Elemente zu erstellen, die mit Systemeinstellungen konsistent sind. <xref:System.Windows.SystemParameters> ist eine Klasse, die sowohl Systemparametern und Ressourcenschlüssel, das Binden an die Werte enthält. Beispielsweise <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ist ein <xref:System.Windows.SystemParameters> Eigenschaftswert und <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> wird der entsprechende Ressourcenschlüssel.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], können Sie die Mitglieder der <xref:System.Windows.SystemParameters> als statische Eigenschaft oder eine dynamische Ressourcenverweise (mit der statischen Eigenschaft-Wert als Schlüssel). Verwenden Sie einen dynamischen Ressourcenverweis, wenn der systembasierte Wert automatisch beim Ausführen der Anwendung aktualisiert werden soll; verwenden Sie andernfalls einen statischen Verweis. / / Ressourcenschlüssel haben das Suffix `Key` des Eigenschaftennamens angefügt.  
  
 Im folgende Beispiel wird gezeigt, wie zugreifen auf und verwenden die statische Werte der <xref:System.Windows.SystemParameters> zu formatieren oder Anpassen einer Schaltfläche. In diesem Markupbeispiel Größen eine Schaltfläche durch Anwenden von <xref:System.Windows.SystemParameters> Werte mit einer Schaltfläche.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Verwenden Sie die Werte der <xref:System.Windows.SystemParameters> in Code können Sie keine statische Verweise oder dynamische Ressourcenverweise zu verwenden. Verwenden Sie stattdessen die Werte der <xref:System.Windows.SystemParameters> Klasse. Obwohl die nicht schlüsselbezogene Eigenschaften als statische Eigenschaften, die das Laufzeitverhalten des offensichtlich definiert sind [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als gehostete vom System wird, wertet die Eigenschaften in Echtzeit und ordnungsgemäß ein Konto, damit Benutzer vorgenommene Änderungen Systemwerte wird. Im folgende Beispiel wird gezeigt, wie die Breite und Höhe einer Schaltfläche festlegen, indem <xref:System.Windows.SystemParameters> Werte.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.SystemParameters>  
 [Zeichnen eines Bereichs mit einem Systempinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Verwenden von SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Verwenden von Systemparameterschlüsseln](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
