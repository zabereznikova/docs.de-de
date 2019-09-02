---
title: Aktivieren der Vervollständigung mit der TAB-TASTE
description: In diesem Artikel erfahren Sie, wie Sie die Vervollständigung mit der TAB-TASTE für die .NET Core-CLI für PowerShell, Bash und zsh aktivieren.
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: c7673d95f3710d78d3a09b26f031396587f9c669
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202503"
---
# <a name="how-to-enable-tab-completion-for-net-core-cli"></a><span data-ttu-id="90cc1-103">Aktivieren der Vervollständigung mit der TAB-TASTE für .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="90cc1-103">How to enable TAB completion for .NET Core CLI</span></span>

<span data-ttu-id="90cc1-104">Ab .NET Core 2.0 SDK unterstützt die .NET Core-CLI die Vervollständigung mit der TAB-TASTE.</span><span class="sxs-lookup"><span data-stu-id="90cc1-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="90cc1-105">In diesem Artikel wird beschrieben, wie Sie die Vervollständigung mit der TAB-TASTE für drei Shells (PowerShell, Bash und zsh) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90cc1-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="90cc1-106">Möglicherweise unterstützen auch andere Shells die automatische Vervollständigung.</span><span class="sxs-lookup"><span data-stu-id="90cc1-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="90cc1-107">Informationen zum Konfigurieren der automatischen Vervollständigung finden Sie in der jeweiligen Dokumentation. Die Schritte sollten den in diesem Artikel beschriebenen Schritten ähneln.</span><span class="sxs-lookup"><span data-stu-id="90cc1-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="90cc1-108">Nach dem Einrichten wird die Vervollständigung mit der TAB-TASTE für die .NET Core-CLI durch Eingeben eines `dotnet`-Befehls in der Shell und anschließendes Drücken der TAB-Taste ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="90cc1-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="90cc1-109">Die aktuelle Befehlszeile wird an den Befehl `dotnet complete` gesendet, und die Ergebnisse werden von der Shell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="90cc1-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="90cc1-110">Sie können die Ergebnisse ohne Aktivierung der Vervollständigung mit der TAB-TASTE testen, indem Sie etwas direkt an den Befehl `dotnet complete` senden.</span><span class="sxs-lookup"><span data-stu-id="90cc1-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="90cc1-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="90cc1-111">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="90cc1-112">Wenn dieser Befehl nicht funktioniert, stellen Sie sicher, dass .NET Core 2.0 SDK oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="90cc1-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="90cc1-113">Wenn es installiert ist, aber dieser Befehl trotzdem nicht funktioniert, vergewissern Sie sich, dass der `dotnet`-Befehl in eine Version von .NET Core 2.0 SDK und höher aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="90cc1-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="90cc1-114">Verwenden Sie den Befehl `dotnet --version`, um festzustellen, in welche Version von `dotnet` der aktuelle Pfad aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="90cc1-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="90cc1-115">Weitere Informationen finden Sie unter [Auswählen der zu verwendenden .NET Core-Version](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="90cc1-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="90cc1-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="90cc1-116">Examples</span></span>

<span data-ttu-id="90cc1-117">Nachfolgend sind einige Beispiele dafür aufgelistet, was durch die Vervollständigung mit der TAB-TASTE bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="90cc1-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="90cc1-118">Eingabe</span><span class="sxs-lookup"><span data-stu-id="90cc1-118">Input</span></span>                                | <span data-ttu-id="90cc1-119">Vervollständigung</span><span class="sxs-lookup"><span data-stu-id="90cc1-119">becomes</span></span>                                                                     | <span data-ttu-id="90cc1-120">Grund</span><span class="sxs-lookup"><span data-stu-id="90cc1-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="90cc1-121">`add` ist der erste Unterbefehl in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="90cc1-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="90cc1-122">Bei der Vervollständigung mit der TAB-TASTE werden Teilzeichenfolgen verglichen, und `--help` ist die erste Übereinstimmung in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="90cc1-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="90cc1-123">Bei erneutem Drücken der TAB-TASTE wird der nächste Vorschlag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90cc1-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="90cc1-124">Ergebnisse werden in alphabetischer Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90cc1-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="90cc1-125">Bei der Vervollständigung mit der TAB-TASTE wird die Projektdatei beachtet.</span><span class="sxs-lookup"><span data-stu-id="90cc1-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="90cc1-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="90cc1-126">PowerShell</span></span>

<span data-ttu-id="90cc1-127">Wenn Sie die Vervollständigung mit der TAB-TASTE zu **PowerShell** für die .NET Core-CLI hinzufügen möchten, erstellen oder bearbeiten Sie das in der Variablen `$PROFILE` gespeicherte Profil.</span><span class="sxs-lookup"><span data-stu-id="90cc1-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="90cc1-128">Weitere Informationen finden Sie unter [Erstellen Ihres Profils](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) und [Profile und Ausführungsrichtlinie](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span><span class="sxs-lookup"><span data-stu-id="90cc1-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="90cc1-129">Fügen Sie Ihrem Profil den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="90cc1-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="90cc1-130">Bash</span><span class="sxs-lookup"><span data-stu-id="90cc1-130">Bash</span></span>

<span data-ttu-id="90cc1-131">Wenn Sie die Vervollständigung mit der TAB-TASTE der **Bash**-Shell für die .NET Core-CLI hinzufügen möchten, fügen Sie der Datei `.bashrc` den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="90cc1-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="90cc1-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="90cc1-132">Zsh</span></span>

<span data-ttu-id="90cc1-133">Wenn Sie die Vervollständigung mit der TAB-TASTE der **zsh**-Shell für die .NET Core-CLI hinzufügen möchten, fügen Sie der Datei `.zshrc` den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="90cc1-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
