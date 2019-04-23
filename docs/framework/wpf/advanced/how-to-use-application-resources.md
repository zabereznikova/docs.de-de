---
title: 'Vorgehensweise: Verwenden von Anwendungsressourcen'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 70dff8089c4da70fdc61247a0c604cf7ee85d02b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088199"
---
# <a name="how-to-use-application-resources"></a>Vorgehensweise: Verwenden von Anwendungsressourcen
In diesem Beispiel wird veranschaulicht, wie Sie Anwendungsressourcen verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Anwendungsdefinitionsdatei. Die Anwendungsdefinitionsdatei definiert einen Ressourcenabschnitt (einen Wert für die <xref:System.Windows.Application.Resources%2A> Eigenschaft). Auf Ressourcen, die auf Anwendungsebene definiert sind, kann von allen anderen Seiten zugegriffen werden, die Teil der Anwendung sind. In diesem Fall ist die Ressource ein deklarierter Stil. Da ein vollständiger Stil, der eine Steuerelementvorlage enthält sehr lang sein kann, lässt in diesem Beispiel die Steuerelementvorlage definiert ist, die die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaftensetter des Stils.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 Das folgende Beispiel zeigt eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite, die die Ressource auf Anwendungsebene verweist, die im vorherige Beispiel definiert. Die Ressource ist auf die verwiesen wird mithilfe einer [StaticResource-Markuperweiterung](staticresource-markup-extension.md) , der den eindeutigen Ressourcenschlüssel für die angeforderte Ressource angibt. Es wird keine Ressource mit dem Schlüssel „GelButton“ auf der aktuellen Seite gefunden, deshalb macht der Ressourcensuchbereich für die angeforderte Ressource über die aktuelle Seite hinaus weiter und in den definierten Ressourcen auf Anwendungsebene.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](xaml-resources.md)
- [Übersicht über die Anwendungsverwaltung](../app-development/application-management-overview.md)
- [Themen zu Vorgehensweisen](resources-how-to-topics.md)
