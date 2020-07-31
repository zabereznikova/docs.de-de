---
title: Clrver.exe (CLR-Versionstool)
description: Informieren Sie sich über das CLR-Versionstool „Clrver.exe“. Dieses Tool führt alle installierten Versionen der Common Language Runtime (CLR) auf dem Computer auf.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: e914034819418df00438c454e209e6c86779ba3c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167272"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="da1f8-104">Clrver.exe (CLR-Versionstool)</span><span class="sxs-lookup"><span data-stu-id="da1f8-104">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="da1f8-105">Das CLR-Versionstool (Clrver.exe) führt alle installierten Versionen der Common Language Runtime (CLR) auf dem Computer auf.</span><span class="sxs-lookup"><span data-stu-id="da1f8-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="da1f8-106">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="da1f8-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="da1f8-107">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="da1f8-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="da1f8-108">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="da1f8-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="da1f8-109">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="da1f8-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da1f8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="da1f8-110">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="da1f8-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="da1f8-111">Options</span></span>  
  
|<span data-ttu-id="da1f8-112">Option</span><span class="sxs-lookup"><span data-stu-id="da1f8-112">Option</span></span>|<span data-ttu-id="da1f8-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da1f8-113">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="da1f8-114">Zeigt alle Prozesse auf dem Computer an, die die CLR verwenden.</span><span class="sxs-lookup"><span data-stu-id="da1f8-114">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="da1f8-115">*pid*</span><span class="sxs-lookup"><span data-stu-id="da1f8-115">*pid*</span></span>|<span data-ttu-id="da1f8-116">Zeigt die Versionen der CLR an, die von dem Prozess verwendet werden, der über angegebene Prozess-ID (PID) aufweist.</span><span class="sxs-lookup"><span data-stu-id="da1f8-116">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="da1f8-117">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="da1f8-117">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da1f8-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="da1f8-118">Remarks</span></span>  
 <span data-ttu-id="da1f8-119">Wenn Sie "Clrver.exe" ohne Optionen aufrufen, werden alle installierten CLR-Versionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da1f8-119">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="da1f8-120">Wenn Sie eine PID für einen anderen Benutzer angeben, müssen Sie über Administratorberechtigungen verfügen, um die Versionsinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da1f8-120">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da1f8-121">Unter Windows Vista (und höher) werden die Berechtigungen eines Benutzers von der Benutzerkontensteuerung (User Account Control, UAC) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="da1f8-121">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="da1f8-122">Als Mitglied der integrierten Administratorgruppe sind Ihnen zwei Zugriffstoken für die Laufzeit zugewiesen: ein Standardbenutzertoken und ein Administratorzugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="da1f8-122">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="da1f8-123">Standardmäßig verwenden Sie die Standardbenutzerrolle.</span><span class="sxs-lookup"><span data-stu-id="da1f8-123">By default, you are in the standard user role.</span></span> <span data-ttu-id="da1f8-124">Um Code ausführen zu können, der Administratorberechtigungen erfordert, müssen Sie zuerst Ihre Berechtigungen von Standardbenutzer auf Administrator erhöhen.</span><span class="sxs-lookup"><span data-stu-id="da1f8-124">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="da1f8-125">Dazu starten Sie die Eingabeaufforderung, indem Sie mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung klicken und angeben, dass Sie die Anwendung als Administrator ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="da1f8-125">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="da1f8-126">Der Versuch, die CLR-Version für SYSTEM-, LOCAL SERVICE- und NETWORK SERVICE-Prozesse zu bestimmen, führt zu einer Meldung, die besagt, dass die PID nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="da1f8-126">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="da1f8-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="da1f8-127">Examples</span></span>  
 <span data-ttu-id="da1f8-128">Mit dem folgenden Befehl werden alle Versionen der CLR angezeigt, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="da1f8-128">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="da1f8-129">Mit dem folgenden Befehl wird die Version der CLR angezeigt, die von Prozess 128 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="da1f8-129">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="da1f8-130">Der folgende Befehl zeigt alle verwalteten Prozesse und die Version der CLR, die sie verwenden, an.</span><span class="sxs-lookup"><span data-stu-id="da1f8-130">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="da1f8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da1f8-131">See also</span></span>

- [<span data-ttu-id="da1f8-132">Extras</span><span class="sxs-lookup"><span data-stu-id="da1f8-132">Tools</span></span>](index.md)
- [<span data-ttu-id="da1f8-133">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="da1f8-133">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
