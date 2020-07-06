---
ms.openlocfilehash: 349854b0dec5a585990b9c5e7c0b575df5bf70f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615730"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a><span data-ttu-id="12519-101">Die XSD-Schemaüberprüfung erkennt jetzt Verstöße gegen eindeutige Einschränkungen richtig, wenn Verbundschlüssel verwendet werden und ein Schlüssel leer ist</span><span class="sxs-lookup"><span data-stu-id="12519-101">XSD Schema validation now correctly detects violations of unique constraints if compound keys are used and one key is empty</span></span>

#### <a name="details"></a><span data-ttu-id="12519-102">Details</span><span class="sxs-lookup"><span data-stu-id="12519-102">Details</span></span>

<span data-ttu-id="12519-103">Versionen von .NET Framework vor 4.6 wiesen einen Fehler auf, der dazu geführt hat, dass die XSD-Validierung eindeutige Einschränkungen für Verbundschlüssel nicht erkannt hat, wenn einer der Schlüssel leer war.</span><span class="sxs-lookup"><span data-stu-id="12519-103">Versions of the .NET Framework prior to 4.6 had a bug that caused XSD validation to not detect unique constraints on compound keys if one of the keys was empty.</span></span> <span data-ttu-id="12519-104">Dieses Problem wurde in .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="12519-104">In the .NET Framework 4.6, this issue is corrected.</span></span> <span data-ttu-id="12519-105">Dies führt zu einwandfreieren Validierung, aber möglicherweise auch dazu, dass einige XML-Daten nicht überprüft werden, die zuvor überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="12519-105">This will result in more correct validation, but it may also result in some XML not validating which previously would have.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="12519-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="12519-106">Suggestion</span></span>

<span data-ttu-id="12519-107">Wenn eine weniger strenge Überprüfung für .NET Framework 4.0 erforderlich ist, kann die überprüfende Anwendung auf Version 4.5 (oder niedriger) von .NET Framework ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="12519-107">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.5 (or earlier) of the .NET Framework.</span></span> <span data-ttu-id="12519-108">Wenn eine Neuausrichtung auf .NET Framework 4.6 erfolgt, sollte jedoch eine Code Review erfolgen, um sicherzustellen, dass die Validierung doppelter Verbundschlüssel (wie in dieser Problembeschreibung erläutert) nicht erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="12519-108">When retargeting to .NET Framework 4.6, however, code review should be done to be sure that duplicate compound keys (as described in this issue's description) are not expected to validate.</span></span>

| <span data-ttu-id="12519-109">Name</span><span class="sxs-lookup"><span data-stu-id="12519-109">Name</span></span>    | <span data-ttu-id="12519-110">Wert</span><span class="sxs-lookup"><span data-stu-id="12519-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="12519-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="12519-111">Scope</span></span>   | <span data-ttu-id="12519-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="12519-112">Edge</span></span>        |
| <span data-ttu-id="12519-113">Version</span><span class="sxs-lookup"><span data-stu-id="12519-113">Version</span></span> | <span data-ttu-id="12519-114">4.6</span><span class="sxs-lookup"><span data-stu-id="12519-114">4.6</span></span>         |
| <span data-ttu-id="12519-115">Typ</span><span class="sxs-lookup"><span data-stu-id="12519-115">Type</span></span>    | <span data-ttu-id="12519-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="12519-116">Retargeting</span></span> |
