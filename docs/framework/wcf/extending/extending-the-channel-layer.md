---
title: Erweitern der Kanalschicht
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending channels [WCF]
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a1a1bb0b1f2c5e6b42ee793f18f5ad442b1fe8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-channel-layer"></a><span data-ttu-id="c74a8-102">Erweitern der Kanalschicht</span><span class="sxs-lookup"><span data-stu-id="c74a8-102">Extending the Channel Layer</span></span>
<span data-ttu-id="c74a8-103">Die Kanalschicht ist für den Nachrichtenaustausch zwischen Clients und Diensten verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="c74a8-103">The channel layer is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="c74a8-104">Durch Kanalerweiterungen können neue Protokollfunktionen implementiert werden, wie beispielsweise Sicherheits- oder Transportfunktionen. So kann zum Beispiel ein neuer Netzwerktransport für die Übermittlung von SOAP-Nachrichten implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c74a8-104">Channel extensions can implement new protocol functionality, such as security, or transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c74a8-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c74a8-105">In This Section</span></span>  
 [<span data-ttu-id="c74a8-106">Übersicht über das Kanalmodell</span><span class="sxs-lookup"><span data-stu-id="c74a8-106">Channel Model Overview</span></span>](../../../../docs/framework/wcf/extending/channel-model-overview.md)  
 <span data-ttu-id="c74a8-107">Gibt einen Überblick über Kanäle, die von ihnen bereitgestellten Funktionen und ihre Funktionsweise in Dienst- und Clientanwendungen.</span><span class="sxs-lookup"><span data-stu-id="c74a8-107">Provides a high-level overview of what channels are, the features that they provide and how they work both in a service and a client application.</span></span>  
  
 [<span data-ttu-id="c74a8-108">Entwickeln von Kanälen</span><span class="sxs-lookup"><span data-stu-id="c74a8-108">Developing Channels</span></span>](../../../../docs/framework/wcf/extending/developing-channels.md)  
 <span data-ttu-id="c74a8-109">Beschreibt detailliert, welche Rolle die einzelnen Kanalinfrastrukturtypen spielen, wie das Statusmodul und der Statuslebenszyklus funktionieren, wie Ausnahmen und Fehler verarbeitet werden, wie die Unterstützung von Metadaten implementiert wird und wie Kanäle mit Nachrichtenencodern zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c74a8-109">Describes in depth the roles that the various channel infrastructure types play, how the state engine and state lifecycle works, how to handle exceptions and faults, how to implement metadata support, and how channels work with message encoders.</span></span>  
  
 [<span data-ttu-id="c74a8-110">Benutzerdefinierte Encoder</span><span class="sxs-lookup"><span data-stu-id="c74a8-110">Custom Encoders</span></span>](../../../../docs/framework/wcf/extending/custom-encoders.md)  
 <span data-ttu-id="c74a8-111">Beschreibt die Rolle der Nachrichtenencoder in Kanälen und ihre Erstellung.</span><span class="sxs-lookup"><span data-stu-id="c74a8-111">Describes the role that message encoders play in channels and how to build one.</span></span>  
  
 [<span data-ttu-id="c74a8-112">Benutzerdefinierte Streamupgrades</span><span class="sxs-lookup"><span data-stu-id="c74a8-112">Custom Stream Upgrades</span></span>](../../../../docs/framework/wcf/extending/custom-stream-upgrades.md)  
 <span data-ttu-id="c74a8-113">Beschreibt, wie Datenströme aktualisiert werden, die von datenstromorientierten Transporten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c74a8-113">Describes the process of upgrading the streams provided by stream-oriented transports.</span></span>
