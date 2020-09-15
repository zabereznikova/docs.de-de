---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614506"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="fd561-101">OperationContext.Current kann NULL zurückgeben, wenn es in einer using-Klausel aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="fd561-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="fd561-102">Details</span><span class="sxs-lookup"><span data-stu-id="fd561-102">Details</span></span>

<span data-ttu-id="fd561-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> kann `null` zurückgeben, und eine <xref:System.NullReferenceException> kann ausgelöst werden, wenn alle folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="fd561-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="fd561-104">Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in einer Methode ab, die entweder <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fd561-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="fd561-105">Sie instanziieren das <xref:System.ServiceModel.OperationContextScope>-Objekt in einer `using`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="fd561-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="fd561-106">Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in `using statement` ab.</span><span class="sxs-lookup"><span data-stu-id="fd561-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="fd561-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fd561-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="fd561-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fd561-108">Suggestion</span></span>

<span data-ttu-id="fd561-109">Dieses Problem können Sie wie folgt beheben:</span><span class="sxs-lookup"><span data-stu-id="fd561-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="fd561-110">Ändern Sie den Code wie folgt, um ein neues <xref:System.ServiceModel.OperationContext.Current%2A>-Objekt zu instanziieren, das nicht `null` ist:</span><span class="sxs-lookup"><span data-stu-id="fd561-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="fd561-111">Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch.</span><span class="sxs-lookup"><span data-stu-id="fd561-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="fd561-112">Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> und stellt das Verhalten von WCF-Anwendungen in .NET Framework 4.6.1 und früheren Versionen wieder her.</span><span class="sxs-lookup"><span data-stu-id="fd561-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="fd561-113">Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="fd561-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="fd561-114">Wenn diese Änderung nicht erwünscht ist und Ihre Anwendung von der Weitergabe des Ausführungskontexts zwischen unterschiedlichen Vorgangskontexten abhängig ist, können Sie die Übertragung wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="fd561-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="fd561-115">name</span><span class="sxs-lookup"><span data-stu-id="fd561-115">Name</span></span>    | <span data-ttu-id="fd561-116">Wert</span><span class="sxs-lookup"><span data-stu-id="fd561-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fd561-117">Bereich</span><span class="sxs-lookup"><span data-stu-id="fd561-117">Scope</span></span>   | <span data-ttu-id="fd561-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fd561-118">Edge</span></span>        |
| <span data-ttu-id="fd561-119">Version</span><span class="sxs-lookup"><span data-stu-id="fd561-119">Version</span></span> | <span data-ttu-id="fd561-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="fd561-120">4.6.2</span></span>       |
| <span data-ttu-id="fd561-121">Typ</span><span class="sxs-lookup"><span data-stu-id="fd561-121">Type</span></span>    | <span data-ttu-id="fd561-122">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="fd561-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="fd561-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fd561-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
