---
title: WS-MetadataExchange-Bindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7267fa8e71a7bbe202bce9897ea09079307be50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="cbbf2-102">WS-MetadataExchange-Bindungen</span><span class="sxs-lookup"><span data-stu-id="cbbf2-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="cbbf2-103">In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="cbbf2-104">Die Standardbindungen</span><span class="sxs-lookup"><span data-stu-id="cbbf2-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="cbbf2-105">Standardbindungsname</span><span class="sxs-lookup"><span data-stu-id="cbbf2-105">Default Binding Name</span></span>|<span data-ttu-id="cbbf2-106">Wie die Bindung erstellt wird</span><span class="sxs-lookup"><span data-stu-id="cbbf2-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="cbbf2-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cbbf2-107">MexHttpBinding</span></span>|<span data-ttu-id="cbbf2-108">Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="cbbf2-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="cbbf2-109">MexHttpsBinding</span></span>|<span data-ttu-id="cbbf2-110">Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="cbbf2-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="cbbf2-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="cbbf2-112">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="cbbf2-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="cbbf2-113">MexTcpBinding</span></span>|<span data-ttu-id="cbbf2-114">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbbf2-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
