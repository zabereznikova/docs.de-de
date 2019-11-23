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
ms.openlocfilehash: 09b33b78ef8f0b62ef4f1e24c56faae783f1e8dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435473"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a>Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter in einer Anwendung implementiert wird.  
  
 Dies ist ein ungewöhnliches Szenario. In der Regel verwendet eine Benutzeroberflächenautomatisierungs-Clientanwendung serverseitige oder clientseitige Anbieter, die sich in einer DLL befinden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird ein einfacher Anbieter für ein Konsolenfenster implementiert. Dieser Code ist nicht auf Funktionalität ausgerichtet, sondern soll die grundlegenden Schritte beim Einrichten eines Anbieters in Clientcode und dessen Registrierung durch <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>veranschaulichen.  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](ui-automation-providers-overview.md)
- [Registrieren einer clientseitigen Anbieterassembly](register-a-client-side-provider-assembly.md)
- [Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](create-a-client-side-ui-automation-provider.md)
- [Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](client-side-ui-automation-provider-implementation.md)
