---
title: WS-MetadataExchange-Bindungen
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293987"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="c18b9-102">WS-MetadataExchange-Bindungen</span><span class="sxs-lookup"><span data-stu-id="c18b9-102">WS-MetadataExchange Bindings</span></span>

<span data-ttu-id="c18b9-103">In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c18b9-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="c18b9-104">Die Standardbindungen</span><span class="sxs-lookup"><span data-stu-id="c18b9-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="c18b9-105">Standardbindungsname</span><span class="sxs-lookup"><span data-stu-id="c18b9-105">Default Binding Name</span></span>|<span data-ttu-id="c18b9-106">Wie die Bindung erstellt wird</span><span class="sxs-lookup"><span data-stu-id="c18b9-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="c18b9-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c18b9-107">mexHttpBinding</span></span>|<span data-ttu-id="c18b9-108">Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="c18b9-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="c18b9-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="c18b9-109">mexHttpsBinding</span></span>|<span data-ttu-id="c18b9-110">Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c18b9-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="c18b9-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="c18b9-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="c18b9-112">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c18b9-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="c18b9-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="c18b9-113">mexTcpBinding</span></span>|<span data-ttu-id="c18b9-114">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c18b9-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
