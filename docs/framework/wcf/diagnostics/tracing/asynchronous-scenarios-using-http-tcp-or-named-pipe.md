---
title: Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 00213c8d117f4319d7e29312dd0b9805d916231a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244144"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="48ab2-102">Asynchrone Szenarien mit HTTP, TCP oder benannten Pipes</span><span class="sxs-lookup"><span data-stu-id="48ab2-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>

<span data-ttu-id="48ab2-103">In diesem Abschnitt werden die Aktivitäten und Übertragungen für verschiedene asynchrone Anforderungs-/Antwortszenarien beschrieben. Dabei werden HTTP, TCP oder benannte Pipes in Multithreadanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="48ab2-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="48ab2-104">Asynchrone Anforderung/Antwort ohne Fehler</span><span class="sxs-lookup"><span data-stu-id="48ab2-104">Asynchronous Request/Reply without Errors</span></span>  

 <span data-ttu-id="48ab2-105">In diesem Abschnitt werden die Aktivitäten und Übertragungen für ein asynchrones Anforderungs-/Antwortszenario mit Multithreadclients beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48ab2-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="48ab2-106">Die aufrufende Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="48ab2-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="48ab2-107">Wenn ein Rückruf aufgerufen wird, wird der Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48ab2-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="48ab2-108">Die aufgerufene Aktivität ist beendet, wenn `beginCall` und `endCall` zurückgegeben werden oder bei Rückgabe des Rückrufs, wenn der Rückruf von dieser Aktivität aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="48ab2-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="48ab2-109">Asynchroner Client ohne Rückruf</span><span class="sxs-lookup"><span data-stu-id="48ab2-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="48ab2-110">Weitergabe wird mit HTTP auf beiden Seiten aktiviert</span><span class="sxs-lookup"><span data-stu-id="48ab2-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  

 ![Asynchroner Client ohne Rückruf, bei dem "propagateActivity" auf beiden Seiten auf "true" festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 <span data-ttu-id="48ab2-112">`propagateActivity=true`Gibt an, dass ProcessMessage angibt, zu welcher ProcessAction-Aktivität übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="48ab2-112">If `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="48ab2-113">Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.</span><span class="sxs-lookup"><span data-stu-id="48ab2-113">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="48ab2-114">Weitergabe wird mit HTTP auf einer der Seiten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="48ab2-114">Propagation is Disabled on Either Sides, using HTTP</span></span>  

 <span data-ttu-id="48ab2-115">`propagateActivity=false`Auf beiden Seiten gibt ProcessMessage nicht an, zu welcher ProcessAction-Aktivität übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="48ab2-115">If `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="48ab2-116">Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="48ab2-116">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="48ab2-117">Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="48ab2-117">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="48ab2-118">Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="48ab2-118">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Asynchroner Client ohne Rückruf, bei dem "propagateActivity" auf jeder Seite auf "false" festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 <span data-ttu-id="48ab2-120">Bei HTTP-basierten Szenarien wird ReceiveBytes zur ersten gesendeten Nachricht aufgerufen und bleibt so lange erhalten wie die Anforderung besteht.</span><span class="sxs-lookup"><span data-stu-id="48ab2-120">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="48ab2-121">Eine Process Action-Aktivität wird auf einem asynchronen Client erstellt, wenn der Aufrufer oder aufgerufener `propagateActivity=false` ist, und wenn die Antwortnachricht keinen Aktions Header enthält.</span><span class="sxs-lookup"><span data-stu-id="48ab2-121">A Process Action activity is created on an asynchronous client when `propagateActivity=false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="48ab2-122">Weitergabe wird mit TCP oder benannten Pipes auf beiden Seiten aktiviert</span><span class="sxs-lookup"><span data-stu-id="48ab2-122">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  

 ![Asynchroner Client ohne Rückruf, bei dem "propagateActivity" auf beiden Seiten und "Named Pipe/TCP" auf "true" festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="48ab2-124">Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="48ab2-124">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="48ab2-125">Ähnlich wie beim ersten Bild `propagateActivity=true` gibt ProcessMessage an, zu welcher ProcessAction-Aktivität übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="48ab2-125">Similar to the first image, if `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="48ab2-126">Weitergabe wird mit TCP oder benannten Pipes auf einer der Seiten deaktiviert</span><span class="sxs-lookup"><span data-stu-id="48ab2-126">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  

 <span data-ttu-id="48ab2-127">Bei auf benannten Pipes oder TCP basierenden Szenarien wird ReceiveBytes beim Öffnen des Clients aufgerufen und bleibt so lange erhalten wie die Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="48ab2-127">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="48ab2-128">Ähnlich wie beim zweiten Bild `propagateActivity=false` gibt ProcessMessage nicht an, zu welcher ProcessAction-Aktivität übertragen werden soll, wenn auf beiden Seiten.</span><span class="sxs-lookup"><span data-stu-id="48ab2-128">Similar to the second image, if `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="48ab2-129">Deshalb wird eine neue temporäre ProcessAction-Aktivität mit einer neuen ID aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="48ab2-129">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="48ab2-130">Wenn die asynchrone Antwort mit der Anforderung im ServiceModel-Code übereinstimmt, kann die Aktivitäts-ID aus dem lokalen Kontext abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="48ab2-130">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="48ab2-131">Die eigentliche ProcessAction-Aktivität kann mit dieser ID übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="48ab2-131">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![Asynchroner Client ohne Rückruf, bei dem "propagateActivity" auf beiden Seiten und Named Pipe/TCP auf "false" festgelegt ist.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="48ab2-133">Asynchroner Client mit Rückruf</span><span class="sxs-lookup"><span data-stu-id="48ab2-133">Asynchronous client with Callback</span></span>  

 <span data-ttu-id="48ab2-134">In diesem Szenario werden für den Rückruf und `endCall` die Aktivitäten G und A' und deren Ein- und Ausgangsübertragung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="48ab2-134">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="48ab2-135">In diesem Abschnitt wird nur die Verwendung von http mit veranschaulicht `propagateActivity` = `true` .</span><span class="sxs-lookup"><span data-stu-id="48ab2-135">This section only demonstrates using HTTP with `propagateActivity`=`true`.</span></span> <span data-ttu-id="48ab2-136">Die zusätzlichen Aktivitäten und Übertragungen gelten jedoch auch für die anderen Fälle (d. h `propagateActivity` = `false` ., mithilfe von TCP oder Named Pipe).</span><span class="sxs-lookup"><span data-stu-id="48ab2-136">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="48ab2-137">Der Rückruf erstellt eine neue Aktivität (G), wenn der Client Benutzercode aufruft, um anzugeben, dass Ergebnisse vorliegen.</span><span class="sxs-lookup"><span data-stu-id="48ab2-137">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="48ab2-138">Der Benutzercode ruft dann `endCall` innerhalb des Rückrufs (siehe Abbildung 5) oder außerhalb des Rückrufs (siehe Abbildung 6) auf</span><span class="sxs-lookup"><span data-stu-id="48ab2-138">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="48ab2-139">Da nicht bekannt ist, aus welcher Benutzeraktivität `endCall` aufgerufen wird, wird diese Aktivität als bezeichnet `A’` .</span><span class="sxs-lookup"><span data-stu-id="48ab2-139">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="48ab2-140">A' kann mit A identisch sein, muss aber nicht.</span><span class="sxs-lookup"><span data-stu-id="48ab2-140">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![Zeigt einen asynchronen Client mit Rückruf, endcallrückruf.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Zeigt einen asynchronen Client mit Rückruf, endcallback außerhalb des Rückrufs.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="48ab2-143">Asynchroner Server mit Rückruf</span><span class="sxs-lookup"><span data-stu-id="48ab2-143">Asynchronous Server with Callback</span></span>  

 ![Zeigt einen asynchronen Server mit Rückruf an.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 <span data-ttu-id="48ab2-145">Der Kanalstapel ruft den Client beim Nachrichtenempfang zurück: Ablaufverfolgungen für diese Verarbeitung werden direkt in der ProcessRequest-Aktivität ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="48ab2-145">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="48ab2-146">Asynchrone Anforderung/Antwort mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="48ab2-146">Asynchronous Request/Reply with Errors</span></span>  

 <span data-ttu-id="48ab2-147">Fehlermeldungen werden während `endCall` empfangen.</span><span class="sxs-lookup"><span data-stu-id="48ab2-147">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="48ab2-148">Davon abgesehen ähneln die Aktivitäten und Übertragungen den vorherigen Szenarien.</span><span class="sxs-lookup"><span data-stu-id="48ab2-148">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="48ab2-149">Asynchrone unidirektional Kommunikation mit oder ohne Fehler</span><span class="sxs-lookup"><span data-stu-id="48ab2-149">Asynchronous One-Way with or without Errors</span></span>  

 <span data-ttu-id="48ab2-150">Keine Antwort oder kein Fehler wird an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48ab2-150">No response or fault is returned to the client.</span></span>
