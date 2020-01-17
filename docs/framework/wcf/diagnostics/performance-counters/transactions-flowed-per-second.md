---
title: Übergegangene Transaktionen pro Sekunde
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: 8b6077af3f98f7a205772b4883dc122374083e00
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163825"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="62706-102">Übergegangene Transaktionen pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="62706-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="62706-103">Indikatorname: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="62706-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="62706-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62706-104">Description</span></span>  
 <span data-ttu-id="62706-105">Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="62706-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="62706-106">Dieser Indikator wird jeweils inkrementiert, wenn eine Transaktions-ID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="62706-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="62706-107">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="62706-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="62706-108">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="62706-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
