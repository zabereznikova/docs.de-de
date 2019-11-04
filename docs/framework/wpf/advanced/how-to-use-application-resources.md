---
title: 'Gewusst wie: Verwenden von Anwendungsressourcen'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460267"
---
# <a name="how-to-use-application-resources"></a>Gewusst wie: Verwenden von Anwendungsressourcen
In diesem Beispiel wird veranschaulicht, wie Sie Anwendungsressourcen verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Anwendungsdefinitionsdatei. Die Anwendungs Definitionsdatei definiert einen Ressourcenabschnitt (einen Wert für die <xref:System.Windows.Application.Resources%2A>-Eigenschaft). Auf Ressourcen, die auf Anwendungsebene definiert sind, kann von allen anderen Seiten zugegriffen werden, die Teil der Anwendung sind. In diesem Fall ist die Ressource ein deklarierter Stil. Da ein kompletter Stil, der eine Steuerelement Vorlage enthält, sehr zeitaufwändiger sein kann, wird in diesem Beispiel die Steuerelement Vorlage ausgelassen, die im <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Eigenschaften Setter des Stils definiert ist.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 Das folgende Beispiel zeigt eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite, die auf die Ressource auf Anwendungsebene verweist, die im vorherigen Beispiel definiert wurde. Auf die Ressource wird mithilfe einer [statikresource-Markup Erweiterung](staticresource-markup-extension.md) verwiesen, die den eindeutigen Ressourcen Schlüssel für die angeforderte Ressource angibt. Es wird keine Ressource mit dem Schlüssel „GelButton“ auf der aktuellen Seite gefunden, deshalb macht der Ressourcensuchbereich für die angeforderte Ressource über die aktuelle Seite hinaus weiter und in den definierten Ressourcen auf Anwendungsebene.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Übersicht über die Anwendungsverwaltung](../app-development/application-management-overview.md)
- [Themen zu Vorgehensweisen](resources-how-to-topics.md)
