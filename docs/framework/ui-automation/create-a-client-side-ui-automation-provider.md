---
title: Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
description: Sehen Sie sich ein Beispiel für das Erstellen eines Client seitigen Benutzeroberflächenautomatisierungs-Anbieters an. Im Beispiel wird ein einfacher Client seitiger Anbieter für ein Konsolenfenster implementiert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: a25966d0f11e409bd4e53f944fc2528360327039
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168473"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter implementiert wird.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode kann in eine Dynamic Link Library (dll) integriert werden, die einen sehr einfachen Client seitigen Anbieter für ein Konsolenfenster implementiert. Der Code enthält keine nützliche Funktionalität, sondern soll die grundlegenden Schritte bei der Einrichtung einer Anbieterassembly veranschaulichen, die über eine Benutzeroberflächenautomatisierungs-Clientanwendung registriert werden kann.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](ui-automation-providers-overview.md)
- [Registrieren einer clientseitigen Anbieterassembly](register-a-client-side-provider-assembly.md)
