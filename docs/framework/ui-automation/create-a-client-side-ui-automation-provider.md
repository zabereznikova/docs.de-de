---
title: "Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5ff3723e016e01b7c249dc7533f2657ea607cd0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="create-a-client-side-ui-automation-provider"></a>Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter implementiert wird.  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode kann in eine [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] integriert werden, die einen sehr einfachen clientseitigen Anbieter für ein Konsolenfenster implementiert. Der Code enthält keine nützliche Funktionalität, sondern soll die grundlegenden Schritte bei der Einrichtung einer Anbieterassembly veranschaulichen, die über eine Benutzeroberflächenautomatisierungs-Clientanwendung registriert werden kann.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Registrieren einer clientseitigen Anbieterassembly](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
