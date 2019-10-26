---
title: Für WCF erforderliche Betriebssystemressourcen
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961133"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="49d9d-102">Für WCF erforderliche Betriebssystemressourcen</span><span class="sxs-lookup"><span data-stu-id="49d9d-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="49d9d-103">Windows Communication Foundation (WCF) hängt von mehreren Ressourcen ab, die vom Betriebssystem zur Funktionsweise bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="49d9d-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="49d9d-104">In der folgenden Tabelle sind diese Ressourcen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="49d9d-104">The following table lists those resources:</span></span>

|<span data-ttu-id="49d9d-105">Ressource</span><span class="sxs-lookup"><span data-stu-id="49d9d-105">Resource</span></span>|<span data-ttu-id="49d9d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49d9d-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="49d9d-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span><span class="sxs-lookup"><span data-stu-id="49d9d-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="49d9d-108">Zur Unterstützung von OleTx-Transaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49d9d-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="49d9d-109">IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="49d9d-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="49d9d-110">Erforderlich, wenn Sie IIS zum Hosten der Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="49d9d-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="49d9d-111">Windows Process Activation Service (WAS)</span><span class="sxs-lookup"><span data-stu-id="49d9d-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="49d9d-112">Erforderlich, wenn Sie WAS zum Hosten der Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="49d9d-112">Required if you want to use WAS to host your application.</span></span>|
