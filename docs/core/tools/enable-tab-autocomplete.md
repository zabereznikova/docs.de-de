---
title: Aktivieren der Vervollständigung mit der TAB-TASTE
description: In diesem Artikel erfahren Sie, wie Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI für PowerShell, Bash und zsh aktivieren.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: 31bf5e74644680fc30ca5b79972fbed6367363e1
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634011"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a><span data-ttu-id="d50c2-103">Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="d50c2-103">How to enable TAB completion for the .NET CLI</span></span>

<span data-ttu-id="d50c2-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d50c2-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="d50c2-105">In diesem Artikel wird beschrieben, wie Sie die Vervollständigung mit der TAB-TASTE für drei Shells (PowerShell, Bash und zsh) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d50c2-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="d50c2-106">Informationen zu anderen Shells und zum Konfigurieren der Vervollständigung mit der TAB-Taste finden Sie in den jeweiligen Dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="d50c2-106">For other shells, refer to their documentation on how to configure tab completion.</span></span>

<span data-ttu-id="d50c2-107">Nach der Einrichtung wird die Vervollständigung mit der TAB-TASTE für die .NET-CLI durch Eingeben eines `dotnet`-Befehls in die Shell und anschließendes Drücken der TAB-Taste ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d50c2-107">Once set up, tab completion for the .NET CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="d50c2-108">Die aktuelle Befehlszeile wird an den Befehl `dotnet complete` gesendet, und die Ergebnisse werden von der Shell verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d50c2-108">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="d50c2-109">Sie können die Ergebnisse ohne Aktivierung der Vervollständigung mit der TAB-TASTE testen, indem Sie etwas direkt an den Befehl `dotnet complete` senden.</span><span class="sxs-lookup"><span data-stu-id="d50c2-109">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="d50c2-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d50c2-110">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="d50c2-111">Wenn dieser Befehl nicht funktioniert, stellen Sie sicher, dass .NET Core 2.0 SDK oder höher installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d50c2-111">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="d50c2-112">Wenn es installiert ist, aber dieser Befehl trotzdem nicht funktioniert, vergewissern Sie sich, dass der `dotnet`-Befehl in eine Version von .NET Core 2.0 SDK und höher aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d50c2-112">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="d50c2-113">Verwenden Sie den Befehl `dotnet --version`, um festzustellen, in welche Version von `dotnet` der aktuelle Pfad aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d50c2-113">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="d50c2-114">Weitere Informationen finden Sie unter [Auswählen der zu verwendenden .NET-Version](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="d50c2-114">For more information, see [Select the .NET version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="d50c2-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d50c2-115">Examples</span></span>

<span data-ttu-id="d50c2-116">Nachfolgend sind einige Beispiele dafür aufgelistet, was durch die Vervollständigung mit der TAB-TASTE bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="d50c2-116">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="d50c2-117">Eingabe</span><span class="sxs-lookup"><span data-stu-id="d50c2-117">Input</span></span>                                | <span data-ttu-id="d50c2-118">Vervollständigung</span><span class="sxs-lookup"><span data-stu-id="d50c2-118">becomes</span></span>                                                                     | <span data-ttu-id="d50c2-119">Grund</span><span class="sxs-lookup"><span data-stu-id="d50c2-119">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="d50c2-120">`add` ist der erste Unterbefehl in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="d50c2-120">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="d50c2-121">Bei der Vervollständigung mit der TAB-TASTE werden Teilzeichenfolgen verglichen, und `--help` ist die erste Übereinstimmung in alphabetischer Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="d50c2-121">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="d50c2-122">Bei erneutem Drücken der TAB-TASTE wird der nächste Vorschlag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d50c2-122">Pressing tab a second time brings up the next suggestion.</span></span>
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="d50c2-123">Ergebnisse werden in alphabetischer Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d50c2-123">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="d50c2-124">Bei der Vervollständigung mit der TAB-TASTE wird die Projektdatei beachtet.</span><span class="sxs-lookup"><span data-stu-id="d50c2-124">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="d50c2-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d50c2-125">PowerShell</span></span>

<span data-ttu-id="d50c2-126">Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zu **PowerShell** hinzufügen möchten, erstellen oder bearbeiten Sie das in der Variablen `$PROFILE` gespeicherte Profil.</span><span class="sxs-lookup"><span data-stu-id="d50c2-126">To add tab completion to **PowerShell** for the .NET CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="d50c2-127">Weitere Informationen finden Sie unter [Erstellen Ihres Profils](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) und [Profile und Ausführungsrichtlinie](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span><span class="sxs-lookup"><span data-stu-id="d50c2-127">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span>

<span data-ttu-id="d50c2-128">Fügen Sie Ihrem Profil den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="d50c2-128">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="d50c2-129">Bash</span><span class="sxs-lookup"><span data-stu-id="d50c2-129">bash</span></span>

<span data-ttu-id="d50c2-130">Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zur **Bash**-Shell hinzufügen möchten, fügen Sie der Datei `.bashrc` den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="d50c2-130">To add tab completion to your **bash** shell for the .NET CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="d50c2-131">zsh</span><span class="sxs-lookup"><span data-stu-id="d50c2-131">zsh</span></span>

<span data-ttu-id="d50c2-132">Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zur **zsh**-Shell hinzufügen möchten, fügen Sie der Datei `.zshrc` den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="d50c2-132">To add tab completion to your **zsh** shell for the .NET CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
