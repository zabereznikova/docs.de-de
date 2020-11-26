---
title: Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 10b9be028710cdda378aeef0ca235a00aa451e08
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243910"
---
# <a name="tracing"></a><span data-ttu-id="f1ec2-102">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f1ec2-102">Tracing</span></span>

<span data-ttu-id="f1ec2-103">Windows Communication Foundation (WCF) stellt Anwendungs Instrumentation und Diagnosedaten für die Fehlerüberwachung und-Analyse bereit.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="f1ec2-104">Sie können die Ablaufverfolgung an Stelle eines Debuggers verwenden, um zu erfahren, wie sich eine Anwendung verhält oder warum sie Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="f1ec2-105">Für ein End-to-End-Ereignis können Sie auch Fehler und Verarbeitung über mehrere Komponenten hinweg korrelieren.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="f1ec2-106">WCF gibt die folgenden Daten für die Diagnose Ablauf Verfolgung aus:</span><span class="sxs-lookup"><span data-stu-id="f1ec2-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
- <span data-ttu-id="f1ec2-107">Ablaufverfolgungen für Verarbeitungsmeilensteine in allen Komponenten der Anwendungen, z.&#160;B. Vorgangsaufrufe, Codeausnahmen, Warnungen und andere wichtige Verarbeitungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
- <span data-ttu-id="f1ec2-108">Windows-Fehlerereignisse bei Fehlern der Ablaufverfolgungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1ec2-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f1ec2-109">In This Section</span></span>  

 [<span data-ttu-id="f1ec2-110">Konfigurieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f1ec2-110">Configuring Tracing</span></span>](configuring-tracing.md)  
  
 <span data-ttu-id="f1ec2-111">In diesem Thema wird beschrieben, wie Sie die Ablaufverfolgung entsprechend Ihren Anforderungen auf verschiedenen Ebenen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="f1ec2-112">End-to-End-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f1ec2-112">End-to-End Tracing</span></span>](end-to-end-tracing.md)  
  
 <span data-ttu-id="f1ec2-113">In diesem Abschnitt wird beschrieben, wie Sie Aktivitätsablaufverfolgung und Weitergabe verwenden können, damit eine End-to-End-Korrelation das Debuggen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="f1ec2-114">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="f1ec2-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="f1ec2-115">In diesem Abschnitt wird beschrieben, wie Sie die Ablaufverfolgung zum Debuggen Ihrer Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="f1ec2-116">Sicherheitsaspekte und nützliche Tipps für die Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f1ec2-116">Security Concerns and Useful Tips for Tracing</span></span>](security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="f1ec2-117">Dieses Thema beschreibt, wie Sie vertrauliche Informationen davor schützen, verfügbar gemacht zu werden, sowie nützliche Tipps zur Verwendung von WebHost.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="f1ec2-118">Referenz für Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="f1ec2-118">Traces Reference</span></span>](traces-reference.md)  
  
 <span data-ttu-id="f1ec2-119">In diesem Thema sind alle von WCF generierten Ablauf Verfolgungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1ec2-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ec2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1ec2-120">See also</span></span>

- [<span data-ttu-id="f1ec2-121">Service Trace Viewer-Tool (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="f1ec2-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
