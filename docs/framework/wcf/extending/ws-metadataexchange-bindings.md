---
title: WS-MetadataExchange-Bindungen
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488623"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="9026f-102">WS-MetadataExchange-Bindungen</span><span class="sxs-lookup"><span data-stu-id="9026f-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="9026f-103">In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9026f-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="9026f-104">Die Standardbindungen</span><span class="sxs-lookup"><span data-stu-id="9026f-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="9026f-105">Standardbindungsname</span><span class="sxs-lookup"><span data-stu-id="9026f-105">Default Binding Name</span></span>|<span data-ttu-id="9026f-106">Wie die Bindung erstellt wird</span><span class="sxs-lookup"><span data-stu-id="9026f-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="9026f-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9026f-107">MexHttpBinding</span></span>|<span data-ttu-id="9026f-108">Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.</span><span class="sxs-lookup"><span data-stu-id="9026f-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="9026f-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="9026f-109">MexHttpsBinding</span></span>|<span data-ttu-id="9026f-110">Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9026f-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="9026f-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="9026f-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="9026f-112">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="9026f-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="9026f-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="9026f-113">MexTcpBinding</span></span>|<span data-ttu-id="9026f-114">Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="9026f-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
