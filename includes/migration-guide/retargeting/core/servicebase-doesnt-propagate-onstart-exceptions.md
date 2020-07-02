---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614522"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="a1aba-101">ServiceBase überträgt OnStart-Ausnahmen nicht</span><span class="sxs-lookup"><span data-stu-id="a1aba-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="a1aba-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1aba-102">Details</span></span>

<span data-ttu-id="a1aba-103">In .NET Framework 4.7 und früheren Versionen werden Ausnahmen, die beim Dienststart ausgelöst werden, nicht an den Aufrufer von <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="a1aba-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="a1aba-104">Beginnend mit Anwendungen, die auf .NET Framework 4.7.1 ausgelegt sind, gibt die Laufzeit Ausnahmen an <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> für Dienste weiter, die nicht gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="a1aba-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1aba-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1aba-105">Suggestion</span></span>

<span data-ttu-id="a1aba-106">Wenn beim Start des Diensts eine Ausnahme auftritt, wird diese Ausnahme weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="a1aba-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="a1aba-107">Dies sollte bei der Diagnose von Fällen helfen, in denen Dienste nicht starten können.</span><span class="sxs-lookup"><span data-stu-id="a1aba-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="a1aba-108">Wenn dieses Verhalten nicht erwünscht ist, können Sie sich dagegen entscheiden, indem Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a1aba-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="a1aba-109">Wenn Ihre Anwendung auf eine frühere Version als 4.7.1 ausgerichtet ist und dieses Verhalten erforderlich ist, können Sie das folgende &lt;AppContextSwitchOverrides&gt;-Element dem Abschnitt &lt;runtime&gt; Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a1aba-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="a1aba-110">name</span><span class="sxs-lookup"><span data-stu-id="a1aba-110">Name</span></span>    | <span data-ttu-id="a1aba-111">Wert</span><span class="sxs-lookup"><span data-stu-id="a1aba-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1aba-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1aba-112">Scope</span></span>   | <span data-ttu-id="a1aba-113">Gering</span><span class="sxs-lookup"><span data-stu-id="a1aba-113">Minor</span></span>       |
| <span data-ttu-id="a1aba-114">Version</span><span class="sxs-lookup"><span data-stu-id="a1aba-114">Version</span></span> | <span data-ttu-id="a1aba-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="a1aba-115">4.7.1</span></span>       |
| <span data-ttu-id="a1aba-116">Typ</span><span class="sxs-lookup"><span data-stu-id="a1aba-116">Type</span></span>    | <span data-ttu-id="a1aba-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="a1aba-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a1aba-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1aba-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
