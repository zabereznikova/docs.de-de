---
ms.openlocfilehash: 3aafb14b65f7c0f9e5d77927809547f9d4b96e1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620372"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="3c971-101">Die Fehlercodes für maxRequestLength oder maxReceivedMessageSize sind unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="3c971-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="3c971-102">Details</span><span class="sxs-lookup"><span data-stu-id="3c971-102">Details</span></span>

<span data-ttu-id="3c971-103">Meldung in WCF-Webdiensten, die in Internetinformationsdiensten (Internet Information Services, IIS) oder in ASP.NET Development Server gehostet werden und maxRequestLength (in ASP.NET) oder maxReceivedMessageSize (in WCF) überschreiten, haben verschiedene Fehlercodes. Der HTTP-Statuscode hat sich von 400 (Ungültige Anforderung) in 413 (Anforderungseinheit zu groß) geändert, und entweder die maxRequestLength- oder die maxReceivedMessageSize-Einstellung löst eine <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3c971-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="3c971-104">Dies gilt auch für Fälle, in denen der Übergangsmodus „Streamed“ ist.</span><span class="sxs-lookup"><span data-stu-id="3c971-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3c971-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3c971-105">Suggestion</span></span>

<span data-ttu-id="3c971-106">Diese Änderung erleichtert das Debuggen in Fällen, in denen die Länge der Meldung die von ASP.NET oder WCF zulässigen Limits überschreiten. Sie müssen sämtlichen Code ändern, der Verarbeitungen auf Grundlage des HTTP-Statuscodes „400“ durchführt.</span><span class="sxs-lookup"><span data-stu-id="3c971-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="3c971-107">name</span><span class="sxs-lookup"><span data-stu-id="3c971-107">Name</span></span>    | <span data-ttu-id="3c971-108">Wert</span><span class="sxs-lookup"><span data-stu-id="3c971-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3c971-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="3c971-109">Scope</span></span>   |<span data-ttu-id="3c971-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3c971-110">Edge</span></span>|
|<span data-ttu-id="3c971-111">Version</span><span class="sxs-lookup"><span data-stu-id="3c971-111">Version</span></span>|<span data-ttu-id="3c971-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3c971-112">4.5</span></span>|
|<span data-ttu-id="3c971-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3c971-113">Type</span></span>|<span data-ttu-id="3c971-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3c971-114">Runtime</span></span>|
