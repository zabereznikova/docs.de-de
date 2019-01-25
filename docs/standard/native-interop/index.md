---
title: Native Interoperabilität – .NET
description: Erfahren Sie, wie Sie eine Verknüpfung mit nativen Komponenten in .NET herstellen.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 29aacc9210b4103f379b7776c36fc3c29b9e6dec
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857618"
---
# <a name="native-interoperability"></a><span data-ttu-id="0012e-103">Native Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="0012e-103">Native interoperability</span></span>

<span data-ttu-id="0012e-104">Im folgenden Artikel werden mehrere Möglichkeiten zur Umsetzung der nativen Interoperabilität in .NET vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="0012e-104">The following articles show the various ways of doing "native interoperability" in .NET.</span></span>

<span data-ttu-id="0012e-105">Es gibt einige Gründe für das Aufrufen von nativem Code:</span><span class="sxs-lookup"><span data-stu-id="0012e-105">There are a few reasons why you'd want to call into native code:</span></span>

* <span data-ttu-id="0012e-106">Betriebssysteme enthalten viele APIs, die in den verwalteten Klassenbibliotheken nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0012e-106">Operating systems come with a large volume of APIs that aren't present in the managed class libraries.</span></span> <span data-ttu-id="0012e-107">Ein gutes Beispiel hierfür ist der Zugriff auf Verwaltungsfunktionen für Hardware oder das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="0012e-107">A prime example for this scenario would be access to hardware or operating system management functions.</span></span>
* <span data-ttu-id="0012e-108">Die Kommunikation mit anderen Komponenten, die ABIs im C-Stil (native ABIs) enthalten oder erstellen können, z. B. Java-Code, der über [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) oder eine andere verwaltete Sprache verfügbar gemacht wird, die eine native Komponente erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0012e-108">Communicating with other components that have or can produce C-style ABIs (native ABIs), such as Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
* <span data-ttu-id="0012e-109">Unter Windows werden für den Großteil der installierten Software (z. B. die Microsoft Office-Suite) COM-Komponenten registriert, die für die Programme stehen und Entwicklern deren Automatisierung oder Verwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0012e-109">On Windows, most of the software that gets installed, such as the Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="0012e-110">Auch hierfür ist native Interoperabilität erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0012e-110">This also requires native interoperability.</span></span>

<span data-ttu-id="0012e-111">Die obige Liste deckt nicht alle möglichen Situationen und Szenarios ab, in denen Entwickler eine Schnittstelle mit nativen Komponenten bevorzugen oder benötigen würden.</span><span class="sxs-lookup"><span data-stu-id="0012e-111">The previous list doesn't cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="0012e-112">Die .NET-Klassenbibliothek verwendet zum Beispiel die Unterstützung für native Interoperabilität, um eine große Anzahl ihrer APIs zu implementieren, z.B. die Unterstützung und Bearbeitung der Konsole, Dateisystemzugriff und mehr.</span><span class="sxs-lookup"><span data-stu-id="0012e-112">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="0012e-113">Nun wissen Sie jedoch, dass Sie diese Option bei Bedarf verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0012e-113">However, it's important to note that there's an option if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="0012e-114">Die meisten Beispiele in diesem Abschnitt werden für alle drei unterstützten Plattformen für .NET Core (Windows, Linux und macOS) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0012e-114">Most of the examples in this section will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="0012e-115">Bei einigen kurzen und anschaulichen Beispielen wird allerdings nur ein Beispiel gezeigt, das Windows-Dateinamen und -Erweiterungen (d.h. „DLL“ für Bibliotheken) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0012e-115">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="0012e-116">Dies wurde nur der Einfachheit halber so gehandhabt und bedeutet nicht, dass diese Funktionen unter Linux oder macOS nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0012e-116">This doesn't mean that those features aren't available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="see-also"></a><span data-ttu-id="0012e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0012e-117">See also</span></span>

- [<span data-ttu-id="0012e-118">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="0012e-118">Platform Invoke (P/Invoke)</span></span>](pinvoke.md)
- [<span data-ttu-id="0012e-119">Marshallen von Typen</span><span class="sxs-lookup"><span data-stu-id="0012e-119">Type marshalling</span></span>](type-marshalling.md)
- [<span data-ttu-id="0012e-120">Bewährte Methoden für native Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="0012e-120">Native interoperability best practices</span></span>](best-practices.md)
