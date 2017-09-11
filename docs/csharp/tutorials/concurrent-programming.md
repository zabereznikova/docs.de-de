---
title: "Parallele Programmierung – Leitfaden für C#"
description: "Lernen Sie Verfahren für die parallele Ausführung von (wahrscheinlich CPU-gebundenen) Aufgaben kennen."
keywords: C#, asynchron, CPU-gebunden, netzwerkgebunden
ms.date: 08/24/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0f8b42de-858a-44a3-87d9-998211f26377
redirect_url: /dotnet/csharp/tutorials/index
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00cf3b04178ca48c9f8f35eb16bc216389e6b272
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="-concurrent-programming"></a><span data-ttu-id="339f9-104">🔧 Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="339f9-104">🔧 Concurrent Programming</span></span>

> <span data-ttu-id="339f9-105">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="339f9-105">**Note**</span></span>
> 
> <span data-ttu-id="339f9-106">Zu diesem Thema wurde noch nichts geschrieben.</span><span class="sxs-lookup"><span data-stu-id="339f9-106">This topic hasn’t been written yet!</span></span> 
>
> <span data-ttu-id="339f9-107">Wir freuen uns auf Ihre Ideen zur Gestaltung des Umfangs und der Herangehensweise.</span><span class="sxs-lookup"><span data-stu-id="339f9-107">We welcome your input to help shape the scope and approach.</span></span> <span data-ttu-id="339f9-108">Sie können den Status nachverfolgen und Informationen zu diesem [Problem](https://github.com/dotnet/docs/issues/953) auf GitHub bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="339f9-108">You can track the status and provide input on this [issue](https://github.com/dotnet/docs/issues/953) at GitHub.</span></span>
> 
> <span data-ttu-id="339f9-109">Wenn Sie früher Entwürfe und Überblicke zu diesem Thema erhalten möchten, geben Sie Ihre Kontaktinformationen bei dem Thema an.</span><span class="sxs-lookup"><span data-stu-id="339f9-109">If you would like to review early drafts and outlines of this topic, please leave a note with your contact information in the issue.</span></span>
>
> <span data-ttu-id="339f9-110">Erfahren Sie mehr darüber, wie Sie zu alledem beitragen können, indem Sie auf [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md) gehen.</span><span class="sxs-lookup"><span data-stu-id="339f9-110">Learn more about how you can contribute on [GitHub](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>
>

