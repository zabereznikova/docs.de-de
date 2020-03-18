---
title: Programmieren austauschbarer Protokolle
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: 94dfedd317782b9e518df02c84d9af55b1ef2b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047402"
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="4b2d7-102">Programmieren austauschbarer Protokolle</span><span class="sxs-lookup"><span data-stu-id="4b2d7-102">Programming Pluggable Protocols</span></span>
<span data-ttu-id="4b2d7-103">Die abstrakten Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> stellen die Grundlage für austauschbare Protokolle bereit.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-103">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="4b2d7-104">Durch Ableiten protokollspezifischer Klassen von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> kann eine Anwendung Daten von einer Internetressource anfordern und die Antwort ohne Angabe des verwendeten Protokolls lesen.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-104">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="4b2d7-105">Vor dem Erstellen einer protokollspezifischen <xref:System.Net.WebRequest> müssen Sie die Create-Methode registrieren.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-105">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="4b2d7-106">Verwenden Sie die statische <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29>-Methode von <xref:System.Net.WebRequest> zur Registrierung eines Nachfolgers von <xref:System.Net.WebRequest>, um eine Reihe von Anforderungen zu behandeln, die an ein bestimmtes Internetschema, an ein Schema und einen Server oder an ein Schema, einen Server und einen Pfad gerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-106">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="4b2d7-107">In den meisten Fällen werden Sie mit den Methoden und Eigenschaften der <xref:System.Net.WebRequest>-Klasse Daten senden und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-107">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="4b2d7-108">Sollten Sie jedoch auf protokollspezifische Eigenschaften zugreifen müssen, können Sie eine Typumwandlung für <xref:System.Net.WebRequest> in eine bestimmte Instanz mit abgeleiteten Klassen durchführen.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-108">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="4b2d7-109">Damit Sie von austauschbaren Protokollen profitieren können, müssen die <xref:System.Net.WebRequest>-Nachfolger eine Standardtransaktion für Anforderung und Antwort bereitstellen, für die keine protokollspezifischen Eigenschaften festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-109">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="4b2d7-110">So stellt beispielsweise die <xref:System.Net.HttpWebRequest>-Klasse, die für HTTP die <xref:System.Net.WebRequest>-Klasse implementiert, standardmäßig eine `GET`-Anforderung bereit und gibt eine <xref:System.Net.HttpWebResponse> zurück, die den vom Webserver zurückgegebenen Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="4b2d7-110">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2d7-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b2d7-111">See also</span></span>

- [<span data-ttu-id="4b2d7-112">Deriving from WebRequest (Ableiten von WebRequest)</span><span class="sxs-lookup"><span data-stu-id="4b2d7-112">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
- [<span data-ttu-id="4b2d7-113">Ableiten von WebResponse</span><span class="sxs-lookup"><span data-stu-id="4b2d7-113">Deriving from WebResponse</span></span>](deriving-from-webresponse.md)
- [<span data-ttu-id="4b2d7-114">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b2d7-114">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="4b2d7-115">Vorgehensweise: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4b2d7-115">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
