---
title: 'Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2fb471a0d91c350bf5df320b8f2ea3b32e74d9ab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Vorgehensweise: Erstellen einer Kanalfactory, mit der ein Kanal erstellt und verwaltet werden kann
Die <xref:System.ServiceModel.DuplexChannelFactory%601>-Klasse ermöglicht das Erstellen und Verwalten von Duplexkanälen verschiedener Typen, die von Clients zum Senden und Empfangen von Nachrichten an bzw. von Dienstendpunkten verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie eine Kanalfactory erstellt und zum Erstellen und Verwalten von Kanälen verwendet wird.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
