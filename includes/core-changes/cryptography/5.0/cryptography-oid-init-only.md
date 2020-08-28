---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558002"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="60362-101">Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="60362-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="60362-102">Die <xref:System.Security.Cryptography.Oid?displayProperty=fullName>-Klasse, die zum Darstellen von ASN.1-Objektbezeichnerwerten und deren „Anzeigenamen“ verwendet wird, war zuvor vollständig änderbar.</span><span class="sxs-lookup"><span data-stu-id="60362-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="60362-103">Diese Veränderlichkeit wurde oft übersehen oder überraschte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="60362-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="60362-104">Die Eigenschaftensetter lösen jetzt eine <xref:System.PlatformNotSupportedException>-Klasse aus, wenn Sie versuchen, den Wert zu ändern, nachdem dieser bereits zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="60362-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="60362-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="60362-105">Change description</span></span>

<span data-ttu-id="60362-106">In früheren Versionen können die Eigenschaftensetter für die <xref:System.Security.Cryptography.Oid>-Klasse verwendet werden, um den Wert der Eigenschaften <xref:System.Security.Cryptography.Oid.FriendlyName> und <xref:System.Security.Cryptography.Oid.Value> zu ändern.</span><span class="sxs-lookup"><span data-stu-id="60362-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="60362-107">In .NET 5.0 und höheren Versionen können die Eigenschaftensetter nur zum Initialisieren eines Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60362-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="60362-108">Wenn die Eigenschaft entweder durch einen Konstruktor oder einen vorherigen Aufruf des Eigenschaftensetters über einen Wert verfügt, löst der Eigenschaftensetter immer eine <xref:System.PlatformNotSupportedException>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="60362-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="60362-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="60362-109">Reason for change</span></span>

<span data-ttu-id="60362-110">Diese Änderung ermöglicht die Wiederverwendung von <xref:System.Security.Cryptography.Oid>-Objekten als Teil der Rückgabewerte in öffentlichen APIs, um Objektzuordnungsprofile zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="60362-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="60362-111">Wenn <xref:System.Security.Cryptography.Oid>-Werte als Eingaben verwendet werden, müssen keine temporären „defensiven“ Kopien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="60362-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="60362-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="60362-112">Version introduced</span></span>

<span data-ttu-id="60362-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="60362-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="60362-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="60362-114">Recommended action</span></span>

<span data-ttu-id="60362-115">Vermeiden Sie die Verwendung der <xref:System.Security.Cryptography.Oid>-Eigenschaftensetter (außer bei der Objektinitialisierung).</span><span class="sxs-lookup"><span data-stu-id="60362-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="60362-116">Verwenden Sie eine neue Instanz, anstatt den Wert für ein vorhandenes Objekt zu ändern, wenn Sie einen neuen Wert darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="60362-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="60362-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="60362-117">Category</span></span>

<span data-ttu-id="60362-118">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="60362-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="60362-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="60362-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
