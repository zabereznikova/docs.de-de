---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614431"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="d490a-101">Aufrufe von ClaimsIdentity-Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="d490a-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="d490a-102">Details</span><span class="sxs-lookup"><span data-stu-id="d490a-102">Details</span></span>

<span data-ttu-id="d490a-103">Ab .NET Framework 4.6.2 legen <xref:System.Security.Claims.ClaimsIdentity>-Konstruktoren mit einem <xref:System.Security.Principal.IIdentity?displayProperty=fullName>-Parameter die Eigenschaft <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> anders fest.</span><span class="sxs-lookup"><span data-stu-id="d490a-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="d490a-104">Wenn es sich bei dem <xref:System.Security.Principal.IIdentity?displayProperty=fullName>-Argument um ein <xref:System.Security.Claims.ClaimsIdentity>-Objekt handelt und die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht `null` ist, wird die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft mithilfe der <xref:System.Security.Claims.ClaimsIdentity.Clone>-Methode angefügt.</span><span class="sxs-lookup"><span data-stu-id="d490a-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="d490a-105">In .NET Framework 4.6.1 und früheren Versionen wurde die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft als vorhandener Verweis angefügt. Aufgrund der Änderung ab .NET Framework 4.6.2 entspricht die <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des neuen <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht der <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>-Eigenschaft des Konstruktorarguments <xref:System.Security.Principal.IIdentity?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d490a-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="d490a-106">In .NET Framework 4.6.1 und früheren Versionen sind die Eigenschaften gleich.</span><span class="sxs-lookup"><span data-stu-id="d490a-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d490a-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d490a-107">Suggestion</span></span>

<span data-ttu-id="d490a-108">Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, indem Sie den `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity`-Schalter in Ihrer Anwendungskonfigurationsdatei auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="d490a-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="d490a-109">Dazu müssen Sie dem Abschnitt `<runtime>` Ihrer web.config-Datei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d490a-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="d490a-110">Name</span><span class="sxs-lookup"><span data-stu-id="d490a-110">Name</span></span>    | <span data-ttu-id="d490a-111">Wert</span><span class="sxs-lookup"><span data-stu-id="d490a-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d490a-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="d490a-112">Scope</span></span>   | <span data-ttu-id="d490a-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d490a-113">Edge</span></span>        |
| <span data-ttu-id="d490a-114">Version</span><span class="sxs-lookup"><span data-stu-id="d490a-114">Version</span></span> | <span data-ttu-id="d490a-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d490a-115">4.6.2</span></span>       |
| <span data-ttu-id="d490a-116">Typ</span><span class="sxs-lookup"><span data-stu-id="d490a-116">Type</span></span>    | <span data-ttu-id="d490a-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d490a-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d490a-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d490a-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
