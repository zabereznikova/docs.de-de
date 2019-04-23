---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804086"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="756e1-101">MEF-Kataloge implementieren IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul zu erstellen</span><span class="sxs-lookup"><span data-stu-id="756e1-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="756e1-102">Details</span><span class="sxs-lookup"><span data-stu-id="756e1-102">Details</span></span>|<span data-ttu-id="756e1-103">Ab .NET Framework 4.5 implementieren MEF-Kataloge IEnumerable und können daher nicht mehr verwendet werden, um ein Serialisierungsmodul (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>-Objekt) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="756e1-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="756e1-104">Wenn Sie versuchen, einen MEF-Katalog zu serialisieren, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="756e1-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="756e1-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="756e1-105">Suggestion</span></span>|<span data-ttu-id="756e1-106">MEF kann nicht mehr zum Erstellen eines Serialisierungsprogramms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="756e1-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="756e1-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="756e1-107">Scope</span></span>|<span data-ttu-id="756e1-108">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="756e1-108">Major</span></span>|
|<span data-ttu-id="756e1-109">Version</span><span class="sxs-lookup"><span data-stu-id="756e1-109">Version</span></span>|<span data-ttu-id="756e1-110">4.5</span><span class="sxs-lookup"><span data-stu-id="756e1-110">4.5</span></span>|
|<span data-ttu-id="756e1-111">Typ</span><span class="sxs-lookup"><span data-stu-id="756e1-111">Type</span></span>|<span data-ttu-id="756e1-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="756e1-112">Runtime</span></span>|
