---
title: Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: 264a24646f7a3c3b5b20e94fa0ed98a1341f8273
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435766"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a>Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, der das Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Anbieter für ein Element veranschaulicht, das sich in einem Fragment befindet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode implementiert <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> für ein Element in einer Liste. Das übergeordnete Element ist das Listenfeldelement und die gleichgeordneten Elemente sind andere Elemente in der Listenauflistung. Die Methode gibt `null` (`Nothing` in Visual Basic) für ungültige Anweisungen zurück. In diesem Fall <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> und <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, da das Element keine untergeordneten Elemente aufweist.  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](ui-automation-providers-overview.md)
- [Server-Side UI Automation Provider Implementation](server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
