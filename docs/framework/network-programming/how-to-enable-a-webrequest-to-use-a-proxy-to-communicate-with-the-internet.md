---
title: 'Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation'
description: Hier erfahren Sie, wie Sie eine globale Proxyinstanz erstellen, damit WebRequest einen Proxy für die Kommunikation mit dem Internet im .NET Framework verwenden kann.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502534"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="b67d7-103">Vorgehensweise: Aktivieren einer WebRequest-Klasse zur Verwendung eines Proxys für die Internetkommunikation</span><span class="sxs-lookup"><span data-stu-id="b67d7-103">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="b67d7-104">In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="b67d7-104">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="b67d7-105">Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.</span><span class="sxs-lookup"><span data-stu-id="b67d7-105">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="b67d7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b67d7-106">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="b67d7-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b67d7-107">Compiling the Code</span></span>

<span data-ttu-id="b67d7-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b67d7-108">This example requires:</span></span>

- <span data-ttu-id="b67d7-109">Eine [`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) in C# für den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="b67d7-109">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="b67d7-110">Eine [`Imports`-Anweisung](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic für den Namespace **System.Net**</span><span class="sxs-lookup"><span data-stu-id="b67d7-110">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="b67d7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b67d7-111">See also</span></span>

- [<span data-ttu-id="b67d7-112">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="b67d7-112">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="b67d7-113">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="b67d7-113">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
