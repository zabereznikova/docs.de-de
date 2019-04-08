---
title: Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105923"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter in einer Anwendung implementiert wird.  
  
 Dies ist ein ungewöhnliches Szenario. In der Regel verwendet eine Benutzeroberflächenautomatisierungs-Clientanwendung serverseitige oder clientseitige Anbieter, die sich in einer DLL befinden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird ein einfacher Anbieter für ein Konsolenfenster implementiert. Dieser Code ist nicht auf Funktionalität ausgerichtet, sondern soll die grundlegenden Schritte beim Einrichten eines Anbieters in Clientcode und dessen Registrierung durch <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>veranschaulichen.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Registrieren einer clientseitigen Anbieterassembly](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
