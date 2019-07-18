---
title: 'Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann'
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: 6ed10cb92af03440848bd29302f8240698d0cbae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039389"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann
Die <xref:System.ServiceModel.DuplexChannelFactory%601>-Klasse ermöglicht das Erstellen und Verwalten von Duplexkanälen verschiedener Typen, die von Clients zum Senden und Empfangen von Nachrichten an bzw. von Dienstendpunkten verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie eine Kanalfactory erstellt und zum Erstellen und Verwalten von Kanälen verwendet wird.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.DuplexChannelFactory%601>
