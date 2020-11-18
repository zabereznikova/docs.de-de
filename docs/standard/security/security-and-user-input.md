---
title: Sicherheit und Benutzereingaben
description: Der Code übergibt möglicherweise vom Benutzer eingegebene Daten als Parameter an anderen Code, was sich auf die Sicherheit auswirken kann. Sie können Bereichs Überprüfungen durchführen, um problematische Eingaben abzulehnen.
ms.date: 07/15/2020
helpviewer_keywords:
- security [.NET], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: e476db90dd1fd579f4ecfe3f2088cc76c955b9c0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824056"
---
# <a name="security-and-user-input"></a><span data-ttu-id="18f98-104">Sicherheit und Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="18f98-104">Security and User Input</span></span>

<span data-ttu-id="18f98-105">Benutzerdaten, bei denen es sich um beliebige Eingaben handeln kann (Daten aus einer Webanforderung oder einer URL, Eingaben in Steuerelemente einer Microsoft Windows Forms-Anwendung usw.), können Code beeinträchtigen, da diese Daten häufig direkt als Parameter zum Aufrufen von anderem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18f98-105">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="18f98-106">Diese Situation ähnelt einem Angriff durch bösartigen Code, der Ihren Code mit ungewöhnlichen Parametern aufruft, weshalb dieselben Vorsichtsmaßnahmen ergriffen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="18f98-106">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="18f98-107">Die Sicherheit bei Benutzereingaben ist sogar schwieriger zu gewährleisten, da kein Stapelrahmen zum Verfolgen der möglicherweise nicht vertrauenswürdigen Daten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="18f98-107">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>

<span data-ttu-id="18f98-108">Diese Sicherheitslücken sind am schwierigsten zu finden, denn obwohl sie sich in Code befinden können, der mit der Sicherheit scheinbar nichts zu tun hat, sind sie dennoch ein Einfallstor für die Übergabe bösartiger Daten an anderen Code.</span><span class="sxs-lookup"><span data-stu-id="18f98-108">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="18f98-109">Um diese Fehler aufzuspüren, verfolgen Sie alle Arten von Eingabedaten, schätzen Sie den Bereich möglicher Werte ein, und ermitteln Sie, ob der Code, der Zugriff auf diese Daten hat, alle diese Fälle behandeln kann.</span><span class="sxs-lookup"><span data-stu-id="18f98-109">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="18f98-110">Sie können diese Fehler beheben, indem Sie Bereiche überprüfen und sämtliche Eingaben zurückweisen, die vom Code nicht behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="18f98-110">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>

<span data-ttu-id="18f98-111">Im Folgenden sind einige wichtige Überlegungen zu Benutzerdaten aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="18f98-111">Some important considerations involving user data include the following:</span></span>

- <span data-ttu-id="18f98-112">Alle Benutzerdaten in einer Serverantwort werden auf dem Client im Kontext der Site des Servers.</span><span class="sxs-lookup"><span data-stu-id="18f98-112">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="18f98-113">Wenn Ihr Webserver Benutzerdaten annimmt und Sie in die zurückgegebene Webseite einfügt, kann er beispielsweise ein **\<script>** Tag einschließen und als if vom Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18f98-113">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>

- <span data-ttu-id="18f98-114">Beachten Sie, dass der Client beliebige URLs anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="18f98-114">Remember that the client can request any URL.</span></span>

- <span data-ttu-id="18f98-115">Berücksichtigen Sie komplizierte oder ungültige Pfade:</span><span class="sxs-lookup"><span data-stu-id="18f98-115">Consider tricky or invalid paths:</span></span>

  - <span data-ttu-id="18f98-116">.. \, äußerst lange Pfade</span><span class="sxs-lookup"><span data-stu-id="18f98-116">..\ , extremely long paths.</span></span>

  - <span data-ttu-id="18f98-117">Verwendung von Platzhalterzeichen (\*)</span><span class="sxs-lookup"><span data-stu-id="18f98-117">Use of wild card characters (\*).</span></span>

  - <span data-ttu-id="18f98-118">Tokenerweiterung (%token%)</span><span class="sxs-lookup"><span data-stu-id="18f98-118">Token expansion (%token%).</span></span>

  - <span data-ttu-id="18f98-119">Ungewöhnliche Formen von Pfaden mit besonderer Bedeutung</span><span class="sxs-lookup"><span data-stu-id="18f98-119">Strange forms of paths with special meaning.</span></span>

  - <span data-ttu-id="18f98-120">Alternative Streamnamen des Dateisystems, z. B. `filename::$DATA`</span><span class="sxs-lookup"><span data-stu-id="18f98-120">Alternate file system stream names such as `filename::$DATA`.</span></span>

  - <span data-ttu-id="18f98-121">Kurze Versionen von Dateinamen, z. B. `longfi~1` für `longfilename`</span><span class="sxs-lookup"><span data-stu-id="18f98-121">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>

- <span data-ttu-id="18f98-122">Denken Sie daran, dass durch Eval(userdata) jede Aktion ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="18f98-122">Remember that Eval(userdata) can do anything.</span></span>

- <span data-ttu-id="18f98-123">Seien Sie vorsichtig bei später Bindung an einen Namen, der Benutzerdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="18f98-123">Be wary of late binding to a name that includes some user data.</span></span>

- <span data-ttu-id="18f98-124">Wenn Sie mit Webdaten arbeiten, müssen die unterschiedlichen Formen von Escapesequenzen berücksichtigen, die zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="18f98-124">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>

  - <span data-ttu-id="18f98-125">Hexadezimale Escapesequenzen (%nn)</span><span class="sxs-lookup"><span data-stu-id="18f98-125">Hexadecimal escapes (%nn).</span></span>

  - <span data-ttu-id="18f98-126">Unicode-Escapesequenzen (%nnn)</span><span class="sxs-lookup"><span data-stu-id="18f98-126">Unicode escapes (%nnn).</span></span>

  - <span data-ttu-id="18f98-127">UTF-8-Escapesequenzen mit Überlänge (%nn%nn)</span><span class="sxs-lookup"><span data-stu-id="18f98-127">Overlong UTF-8 escapes (%nn%nn).</span></span>

  - <span data-ttu-id="18f98-128">Doppelte Escapesequenzen (%nn wird zu %mmnn, wobei %mm die Escapesequenz für „%“ ist)</span><span class="sxs-lookup"><span data-stu-id="18f98-128">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>

- <span data-ttu-id="18f98-129">Besondere Vorsicht ist bei Benutzernamen geboten, die mehrere kanonische Formen haben können.</span><span class="sxs-lookup"><span data-stu-id="18f98-129">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="18f98-130">Beispielsweise können Sie häufig entweder die Form MYDOMAIN\\*Benutzername* oder die Form *Benutzername*@mydomain.example.com verwenden.</span><span class="sxs-lookup"><span data-stu-id="18f98-130">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>

## <a name="see-also"></a><span data-ttu-id="18f98-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18f98-131">See also</span></span>

- [<span data-ttu-id="18f98-132">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="18f98-132">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
- [<span data-ttu-id="18f98-133">ASP.net Core Sicherheit</span><span class="sxs-lookup"><span data-stu-id="18f98-133">ASP.NET Core Security</span></span>](/aspnet/core/security/)
