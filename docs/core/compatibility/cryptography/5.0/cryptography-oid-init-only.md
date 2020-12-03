---
title: 'Breaking Change: Cryptography.OID ist funktional ein Nur-init-Setter'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Eigenschaftensetter in der Klasse „Cryptography.Oid“ nun eine Ausnahme auslösen, wenn Sie versuchen, einen Wert zu ändern.
ms.date: 08/16/2020
ms.openlocfilehash: a3b5a393e2a84f7c9a60c2a821ecfda9c6acd2e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759226"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="103ef-103">Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="103ef-103">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="103ef-104">Die <xref:System.Security.Cryptography.Oid?displayProperty=fullName>-Klasse, die zum Darstellen von ASN.1-Objektbezeichnerwerten und deren „Anzeigenamen“ verwendet wird, war zuvor vollständig änderbar.</span><span class="sxs-lookup"><span data-stu-id="103ef-104">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="103ef-105">Diese Veränderlichkeit wurde oft übersehen oder überraschte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="103ef-105">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="103ef-106">Die Eigenschaftensetter lösen jetzt eine <xref:System.PlatformNotSupportedException>-Klasse aus, wenn Sie versuchen, den Wert zu ändern, nachdem dieser bereits zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="103ef-106">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

## <a name="change-description"></a><span data-ttu-id="103ef-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="103ef-107">Change description</span></span>

<span data-ttu-id="103ef-108">In früheren Versionen können die Eigenschaftensetter für die <xref:System.Security.Cryptography.Oid>-Klasse verwendet werden, um den Wert der Eigenschaften <xref:System.Security.Cryptography.Oid.FriendlyName> und <xref:System.Security.Cryptography.Oid.Value> zu ändern.</span><span class="sxs-lookup"><span data-stu-id="103ef-108">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="103ef-109">In .NET 5.0 und höheren Versionen können die Eigenschaftensetter nur zum Initialisieren eines Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="103ef-109">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="103ef-110">Wenn die Eigenschaft entweder durch einen Konstruktor oder einen vorherigen Aufruf des Eigenschaftensetters über einen Wert verfügt, löst der Eigenschaftensetter immer eine <xref:System.PlatformNotSupportedException>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="103ef-110">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="103ef-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="103ef-111">Reason for change</span></span>

<span data-ttu-id="103ef-112">Diese Änderung ermöglicht die Wiederverwendung von <xref:System.Security.Cryptography.Oid>-Objekten als Teil der Rückgabewerte in öffentlichen APIs, um Objektzuordnungsprofile zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="103ef-112">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="103ef-113">Wenn <xref:System.Security.Cryptography.Oid>-Werte als Eingaben verwendet werden, müssen keine temporären „defensiven“ Kopien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="103ef-113">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="103ef-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="103ef-114">Version introduced</span></span>

<span data-ttu-id="103ef-115">5.0</span><span class="sxs-lookup"><span data-stu-id="103ef-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="103ef-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="103ef-116">Recommended action</span></span>

<span data-ttu-id="103ef-117">Vermeiden Sie die Verwendung der <xref:System.Security.Cryptography.Oid>-Eigenschaftensetter (außer bei der Objektinitialisierung).</span><span class="sxs-lookup"><span data-stu-id="103ef-117">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="103ef-118">Verwenden Sie eine neue Instanz, anstatt den Wert für ein vorhandenes Objekt zu ändern, wenn Sie einen neuen Wert darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="103ef-118">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="103ef-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="103ef-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
