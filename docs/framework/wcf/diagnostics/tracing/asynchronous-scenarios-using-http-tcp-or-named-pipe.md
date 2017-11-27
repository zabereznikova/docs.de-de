---
title: Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c697069aad590013ff360eb6ee4cba39468b89d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="ed646-102">Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes</span><span class="sxs-lookup"><span data-stu-id="ed646-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="ed646-103">In diesem Abschnitt werden die Aktivitäten und Übertragungen für verschiedene asynchrone Anforderungs-/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes in Multithreadanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed646-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="ed646-104">Asynchrone Anforderung/Antwort ohne Fehler</span><span class="sxs-lookup"><span data-stu-id="ed646-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="ed646-105">In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein asynchrones Anforderungs-/Antwortszenario mit Multithreadclients beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed646-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="ed646-106">Die aufrufende Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed646-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="ed646-107">Wenn ein Rückruf aufgerufen wird, wird der Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed646-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="ed646-108">Die aufgerufene Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden oder bei Rückgabe des Rückrufs, wenn der Rückruf von dieser Aktivität aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ed646-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="ed646-109">Asynchroner Client ohne Rückruf</span><span class="sxs-lookup"><span data-stu-id="ed646-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="ed646-110">Weitergabe wird mit HTTP auf beiden Seiten aktiviert</span><span class="sxs-lookup"><span data-stu-id="ed646-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 <span data-ttu-id="ed646-111">![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span><span class="sxs-lookup"><span data-stu-id="ed646-111">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span></span>  
  
 <span data-ttu-id="ed646-112">Abbildung 1.</span><span class="sxs-lookup"><span data-stu-id="ed646-112">Figure 1.</span></span> <span data-ttu-id="ed646-113">Asynchroner Client, kein Rückruf, `propagateActivity` = `true` auf beiden Seiten, HTTP</span><span class="sxs-lookup"><span data-stu-id="ed646-113">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, HTTP</span></span>  
  
 <span data-ttu-id="ed646-114">Wenn `propagateActivity` = `true`, gibt ProcessMessage an, ProcessAction-Aktivität zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="ed646-114">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="ed646-115">Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.</span><span class="sxs-lookup"><span data-stu-id="ed646-115">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="ed646-116">Weitergabe wird mit HTTP auf einer der Seiten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="ed646-116">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="ed646-117">Wenn `propagateActivity` = `false` auf beiden Seiten ProcessMessage nicht an die ProcessAction-Aktivität die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="ed646-117">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="ed646-118">Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed646-118">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="ed646-119">Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed646-119">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="ed646-120">Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ed646-120">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="ed646-121">![Asynchrone Szenarien mit HTTP- &#47; TCP &#47; Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span><span class="sxs-lookup"><span data-stu-id="ed646-121">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span></span>  
  
 <span data-ttu-id="ed646-122">Abbildung 2.</span><span class="sxs-lookup"><span data-stu-id="ed646-122">Figure 2.</span></span> <span data-ttu-id="ed646-123">Asynchroner Client, kein Rückruf, `propagateActivity` = `false` auf einer Seite, HTTP</span><span class="sxs-lookup"><span data-stu-id="ed646-123">Asynchronous client, no callback, `propagateActivity`=`false` on either side, HTTP</span></span>  
  
 <span data-ttu-id="ed646-124">Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.</span><span class="sxs-lookup"><span data-stu-id="ed646-124">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="ed646-125">Eine Processaction-Aktivität wird für einen asynchronen Client erstellt beim `propagateActivity` = `false` an den Aufrufer oder aufgerufene, und wenn die Antwortnachricht Action-Header nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ed646-125">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="ed646-126">Weitergabe wird mit TCP oder benannten Pipes auf beiden Seiten aktiviert</span><span class="sxs-lookup"><span data-stu-id="ed646-126">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="ed646-127">![Asynchrone Szenarien mit HTTP- &#47; TCP &#47; Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span><span class="sxs-lookup"><span data-stu-id="ed646-127">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span></span>  
  
 <span data-ttu-id="ed646-128">Abbildung 3.</span><span class="sxs-lookup"><span data-stu-id="ed646-128">Figure 3.</span></span> <span data-ttu-id="ed646-129">Asynchroner Client, kein Rückruf, `propagateActivity` = `true` auf beiden Seiten, benannte Pipes/TCP</span><span class="sxs-lookup"><span data-stu-id="ed646-129">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, Named-Pipe/TCP</span></span>  
  
 <span data-ttu-id="ed646-130">Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="ed646-130">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="ed646-131">Abbildung 1, wenn ähnelt `propagateActivity` = `true`, gibt ProcessMessage an, ProcessAction-Aktivität zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="ed646-131">Similar to Figure 1, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="ed646-132">Weitergabe wird mit TCP oder benannten Pipes auf einer der Seiten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="ed646-132">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="ed646-133">Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="ed646-133">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="ed646-134">Ähnlich wie in Abbildung 2, wenn `propagateActivity` = `false` auf beiden Seiten ProcessMessage nicht an die ProcessAction-Aktivität die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="ed646-134">Similar to Fig.2, If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="ed646-135">Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ed646-135">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="ed646-136">Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed646-136">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="ed646-137">Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ed646-137">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="ed646-138">![Asynchrone Szenarien mit HTTP- &#47; TCP &#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span><span class="sxs-lookup"><span data-stu-id="ed646-138">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span></span>  
  
 <span data-ttu-id="ed646-139">Abbildung 4.</span><span class="sxs-lookup"><span data-stu-id="ed646-139">Figure 4.</span></span> <span data-ttu-id="ed646-140">Asynchroner Client, kein Rückruf, `propagateActivity` = `false` auf beiden Seiten, benannte Pipes/TCP</span><span class="sxs-lookup"><span data-stu-id="ed646-140">Asynchronous client, no callback, `propagateActivity`=`false` on either side, Named-Pipe/TCP</span></span>  
  
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="ed646-141">Asynchroner Client mit Rückruf</span><span class="sxs-lookup"><span data-stu-id="ed646-141">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="ed646-142">In diesem Szenario werden für den Rückruf und `endCall` die Aktivitäten G und A' und deren Ein- und Ausgangsübertragung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ed646-142">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="ed646-143">Dieser Abschnitt veranschaulicht lediglich die Verwendung von HTTP mit `propragateActivity` = `true`.</span><span class="sxs-lookup"><span data-stu-id="ed646-143">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="ed646-144">Die zusätzlichen Aktivitäten und Übertragungen treffen jedoch auch auf die anderen Fälle (d. h. `propagateActivity` = `false`, mit TCP oder benannten Pipes).</span><span class="sxs-lookup"><span data-stu-id="ed646-144">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="ed646-145">Der Rückruf erstellt eine neue Aktivität (G), wenn der Client Benutzercode aufruft, um anzugeben, dass Ergebnisse vorliegen.</span><span class="sxs-lookup"><span data-stu-id="ed646-145">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="ed646-146">Der Benutzercode ruft dann `endCall` innerhalb des Rückrufs (siehe Abbildung 5) oder außerhalb des Rückrufs (siehe Abbildung 6) auf</span><span class="sxs-lookup"><span data-stu-id="ed646-146">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="ed646-147">Da die Benutzeraktivität nicht bekannt ist `endCall` aufgerufen wird, diese Aktivität ist mit der Bezeichnung `A’`.</span><span class="sxs-lookup"><span data-stu-id="ed646-147">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="ed646-148">A' kann mit A identisch sein, muss aber nicht.</span><span class="sxs-lookup"><span data-stu-id="ed646-148">It is possible that A’ can be identical to or different from A.</span></span>  
  
 <span data-ttu-id="ed646-149">![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span><span class="sxs-lookup"><span data-stu-id="ed646-149">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span></span>  
  
 <span data-ttu-id="ed646-150">Abbildung 5.</span><span class="sxs-lookup"><span data-stu-id="ed646-150">Figure 5.</span></span> <span data-ttu-id="ed646-151">Asynchroner Client mit Rückruf, `endCall` im Rückruf</span><span class="sxs-lookup"><span data-stu-id="ed646-151">Asynchronous client with callback, `endCall` in Callback</span></span>  
  
 <span data-ttu-id="ed646-152">![Asynchrone Szenarien](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span><span class="sxs-lookup"><span data-stu-id="ed646-152">![Asynchronous Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span></span>  
  
 <span data-ttu-id="ed646-153">Abbildung 6.</span><span class="sxs-lookup"><span data-stu-id="ed646-153">Figure 6.</span></span> <span data-ttu-id="ed646-154">Asynchroner Client mit Rückruf, `endCall` außerhalb des Rückrufs</span><span class="sxs-lookup"><span data-stu-id="ed646-154">Asynchronous client with callback, `endCall` outside of Callback</span></span>  
  
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="ed646-155">Asynchroner Server mit Rückruf</span><span class="sxs-lookup"><span data-stu-id="ed646-155">Asynchronous Server with Callback</span></span>  
 <span data-ttu-id="ed646-156">![Asynchrone Szenarien mit HTTP- &#47; TCP &#47; Mit dem Namen &#45; Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span><span class="sxs-lookup"><span data-stu-id="ed646-156">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span></span>  
  
 <span data-ttu-id="ed646-157">Abbildung 7.</span><span class="sxs-lookup"><span data-stu-id="ed646-157">Figure 7.</span></span> <span data-ttu-id="ed646-158">Asynchroner Server mit Rückruf</span><span class="sxs-lookup"><span data-stu-id="ed646-158">Asynchronous server, with callback</span></span>  
  
 <span data-ttu-id="ed646-159">Der Kanalstapel ruft den Client beim Nachrichtenempfang zurück: Ablaufverfolgungen für diese Verarbeitung werden direkt in der ProcessRequest-Aktivität ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed646-159">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="ed646-160">Asynchrone Anforderung/Antwort mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="ed646-160">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="ed646-161">Fehlermeldungen werden während `endCall` empfangen.</span><span class="sxs-lookup"><span data-stu-id="ed646-161">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="ed646-162">Davon abgesehen ähneln die Aktivitäten und Übertragungen den vorherigen Szenarien.</span><span class="sxs-lookup"><span data-stu-id="ed646-162">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="ed646-163">Asynchrone unidirektional Kommunikation mit oder ohne Fehler</span><span class="sxs-lookup"><span data-stu-id="ed646-163">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="ed646-164">Keine Antwort oder kein Fehler wird an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed646-164">No response or fault is returned to the client.</span></span>
