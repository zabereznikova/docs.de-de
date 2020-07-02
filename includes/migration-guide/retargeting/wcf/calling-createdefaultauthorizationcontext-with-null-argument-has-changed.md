---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615707"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="c4eff-101">Das Aufrufen von CreateDefaultAuthorizationContext mit einem NULL-Argument wurde geändert</span><span class="sxs-lookup"><span data-stu-id="c4eff-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="c4eff-102">Details</span><span class="sxs-lookup"><span data-stu-id="c4eff-102">Details</span></span>

<span data-ttu-id="c4eff-103">Die Implementierung des <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>-Elements, das von einem Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> mit dem NULL-Wert als Argument „authorizationPolicies“ zurückgegeben wurde, hat seine Implementierung in .NET Framework 4.6 geändert.</span><span class="sxs-lookup"><span data-stu-id="c4eff-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c4eff-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c4eff-104">Suggestion</span></span>

<span data-ttu-id="c4eff-105">In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor.</span><span class="sxs-lookup"><span data-stu-id="c4eff-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="c4eff-106">In derartigen Fällen gibt es zwei Möglichkeiten, um das vorherige Verhalten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="c4eff-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="c4eff-107">Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt.</span><span class="sxs-lookup"><span data-stu-id="c4eff-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="c4eff-108">Verwenden Sie für mithilfe von IIS gehosteten Diensten das `<httpRuntime targetFramework="x.x">`-Element, um auf eine frühere Version von .NET Framework abzuzielen.</span><span class="sxs-lookup"><span data-stu-id="c4eff-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="c4eff-109">Fügen Sie dem Abschnitt `<appSettings>` Ihrer Datei „app.config“ die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="c4eff-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="c4eff-110">name</span><span class="sxs-lookup"><span data-stu-id="c4eff-110">Name</span></span>    | <span data-ttu-id="c4eff-111">Wert</span><span class="sxs-lookup"><span data-stu-id="c4eff-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c4eff-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="c4eff-112">Scope</span></span>   | <span data-ttu-id="c4eff-113">Gering</span><span class="sxs-lookup"><span data-stu-id="c4eff-113">Minor</span></span>       |
| <span data-ttu-id="c4eff-114">Version</span><span class="sxs-lookup"><span data-stu-id="c4eff-114">Version</span></span> | <span data-ttu-id="c4eff-115">4.6</span><span class="sxs-lookup"><span data-stu-id="c4eff-115">4.6</span></span>         |
| <span data-ttu-id="c4eff-116">Typ</span><span class="sxs-lookup"><span data-stu-id="c4eff-116">Type</span></span>    | <span data-ttu-id="c4eff-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="c4eff-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c4eff-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c4eff-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
