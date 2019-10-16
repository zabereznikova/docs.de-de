---
title: Calls Faulted Per Second
ms.date: 03/30/2017
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
ms.openlocfilehash: 424e658c2f8243fae1b4ebef8d98c57681166a67
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321083"
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="a48b9-102">Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="a48b9-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="a48b9-103">Indikatorname: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="a48b9-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="a48b9-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a48b9-104">Description</span></span>  
 <span data-ttu-id="a48b9-105">Die Anzahl der Aufrufe, die in einer Sekunde an diesen Vorgang Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a48b9-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="a48b9-106">Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert mit der folgenden Formel berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="a48b9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a48b9-107">(N 1 - N 0)/( (D 1 - D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="a48b9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="a48b9-108">In Windows Communication Foundation (WCF)-Anwendungen übermitteln Dienst Methoden Verarbeitungsfehler Informationen mithilfe von SOAP-Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="a48b9-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="a48b9-109">SOAP-Fehler sind Meldungstypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="a48b9-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="a48b9-110">Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, sind sie sehr interoperabel.</span><span class="sxs-lookup"><span data-stu-id="a48b9-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48b9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a48b9-111">See also</span></span>

- [<span data-ttu-id="a48b9-112">Angeben und Behandeln von Fehlern in Verträgen und Diensten</span><span class="sxs-lookup"><span data-stu-id="a48b9-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
