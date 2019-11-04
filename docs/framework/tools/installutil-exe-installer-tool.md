---
title: Installutil.exe (Installer-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: caca946617c681ce6516b7184a9ea506cc67158d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105071"
---
# <a name="installutilexe-installer-tool"></a><span data-ttu-id="c715f-102">Installutil.exe (Installer-Tool)</span><span class="sxs-lookup"><span data-stu-id="c715f-102">Installutil.exe (Installer Tool)</span></span>

<span data-ttu-id="c715f-103">Das Installationsprogrammtool ist ein Befehlszeilen-Hilfsprogramm, mit dem Sie Serverressourcen installieren und deinstallieren können, indem Sie die Komponenten des Installationsprogramms in angegebenen Assemblys ausführen.</span><span class="sxs-lookup"><span data-stu-id="c715f-103">The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing the installer components in specified assemblies.</span></span> <span data-ttu-id="c715f-104">Dieses Tool funktioniert in Verbindung mit Klassen im <xref:System.Configuration.Install>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="c715f-104">This tool works in conjunction with classes in the <xref:System.Configuration.Install> namespace.</span></span>

<span data-ttu-id="c715f-105">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="c715f-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c715f-106">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c715f-106">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c715f-107">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c715f-107">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="c715f-108">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c715f-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="c715f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c715f-109">Syntax</span></span>

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a><span data-ttu-id="c715f-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="c715f-110">Parameters</span></span>

|<span data-ttu-id="c715f-111">Argument</span><span class="sxs-lookup"><span data-stu-id="c715f-111">Argument</span></span>|<span data-ttu-id="c715f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c715f-112">Description</span></span>|
|--------------|-----------------|
|`assembly`|<span data-ttu-id="c715f-113">Der Dateiname der Assembly, in der die Installationsprogrammkomponenten ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c715f-113">The file name of the assembly in which to execute the installer components.</span></span> <span data-ttu-id="c715f-114">Lassen Sie diesen Parameter aus, wenn Sie den starken Namen der Assembly angeben möchten, indem Sie die `/AssemblyName`-Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="c715f-114">Omit this parameter if you want to specify the assembly's strong name by using the `/AssemblyName` option.</span></span>|

<a name="options"></a>

## <a name="options"></a><span data-ttu-id="c715f-115">Optionen</span><span class="sxs-lookup"><span data-stu-id="c715f-115">Options</span></span>

|<span data-ttu-id="c715f-116">Option</span><span class="sxs-lookup"><span data-stu-id="c715f-116">Option</span></span>|<span data-ttu-id="c715f-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c715f-117">Description</span></span>|
|------------|-----------------|
|`/h[elp]`<br /><br /> <span data-ttu-id="c715f-118">Oder</span><span class="sxs-lookup"><span data-stu-id="c715f-118">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="c715f-119">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="c715f-119">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="c715f-120">`/help` *assembly*</span><span class="sxs-lookup"><span data-stu-id="c715f-120">`/help` *assembly*</span></span><br /><br /> <span data-ttu-id="c715f-121">Oder</span><span class="sxs-lookup"><span data-stu-id="c715f-121">-or-</span></span><br /><br /> <span data-ttu-id="c715f-122">`/?` *assembly*</span><span class="sxs-lookup"><span data-stu-id="c715f-122">`/?` *assembly*</span></span>|<span data-ttu-id="c715f-123">Zeigt zusätzliche Optionen, die von einzelnen Installationsprogrammen innerhalb der angegebenen Assembly erkannt werden, zusammen mit der Befehlssyntax und Optionen für "InstallUtil.exe" an.</span><span class="sxs-lookup"><span data-stu-id="c715f-123">Displays additional options recognized by individual installers within the specified assembly, along with command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="c715f-124">Mit dieser Option wird dem Hilfetext von "InstallUtil.exe" der von der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft aller Installationsprogrammkomponenten zurückgegebene Text hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c715f-124">This option adds the text returned by each installer component's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property to the help text of InstallUtil.exe.</span></span>|
|<span data-ttu-id="c715f-125">`/AssemblyName` "*assemblyName*</span><span class="sxs-lookup"><span data-stu-id="c715f-125">`/AssemblyName` "*assemblyName*</span></span><br /><br /> <span data-ttu-id="c715f-126">,Version=*major.minor.build.revision*</span><span class="sxs-lookup"><span data-stu-id="c715f-126">,Version=*major.minor.build.revision*</span></span><br /><br /> <span data-ttu-id="c715f-127">,Culture=*locale*</span><span class="sxs-lookup"><span data-stu-id="c715f-127">,Culture=*locale*</span></span><br /><br /> <span data-ttu-id="c715f-128">,PublicKeyToken=*publicKeyToken*"</span><span class="sxs-lookup"><span data-stu-id="c715f-128">,PublicKeyToken=*publicKeyToken*"</span></span>|<span data-ttu-id="c715f-129">Gibt den starken Namen einer Assembly an, die im globalen Assemblycache registriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c715f-129">Specifies the strong name of an assembly, which must be registered in the global assembly cache.</span></span> <span data-ttu-id="c715f-130">Der Assemblyname muss mit der Version, Kultur und dem öffentlichen Schlüsseltoken der Assembly vollständig qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-130">The assembly name must be fully qualified with the version, culture, and public key token of the assembly.</span></span> <span data-ttu-id="c715f-131">Der vollqualifizierte Name muss in Anführungszeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="c715f-131">The fully qualified name must be surrounded by quotes.</span></span><br /><br /> <span data-ttu-id="c715f-132">"myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" ist beispielsweise ein vollqualifizierter Assemblyname.</span><span class="sxs-lookup"><span data-stu-id="c715f-132">For example, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" is a fully qualified assembly name.</span></span>|
|<span data-ttu-id="c715f-133">`/InstallStateDir=[` *directoryName* `]`</span><span class="sxs-lookup"><span data-stu-id="c715f-133">`/InstallStateDir=[` *directoryName* `]`</span></span>|<span data-ttu-id="c715f-134">Gibt das Verzeichnis der INSTALLSTATE-Datei an, die die Daten enthält, die verwendet werden, um die Assembly zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c715f-134">Specifies the directory of the .InstallState file that contains the data used to uninstall the assembly.</span></span> <span data-ttu-id="c715f-135">Das Standardverzeichnis ist das Verzeichnis, das die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c715f-135">The default is the directory that contains the assembly.</span></span>|
|<span data-ttu-id="c715f-136">`/LogFile=`[*filename*]</span><span class="sxs-lookup"><span data-stu-id="c715f-136">`/LogFile=`[*filename*]</span></span>|<span data-ttu-id="c715f-137">Gibt den Namen der Protokolldatei an, in der der Installationsverlauf aufgezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c715f-137">Specifies the name of the log file where installation progress is recorded.</span></span> <span data-ttu-id="c715f-138">Wenn die Option `/LogFile` fehlt, wird standardmäßig die Protokolldatei „*assemblyname*.InstallLog“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="c715f-138">By default, if the `/LogFile` option is omitted, a log file named *assemblyname*.InstallLog is created.</span></span> <span data-ttu-id="c715f-139">Wenn *filename* nicht angegeben wird, wird keine Protokolldatei generiert.</span><span class="sxs-lookup"><span data-stu-id="c715f-139">If *filename* is omitted, no log file is generated.</span></span>|
|<span data-ttu-id="c715f-140">`/LogToConsole`={`true`&#124;`false`}</span><span class="sxs-lookup"><span data-stu-id="c715f-140">`/LogToConsole`={`true`&#124;`false`}</span></span>|<span data-ttu-id="c715f-141">Wenn der Wert `true` ist, wird die Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c715f-141">If `true`, displays output to the console.</span></span> <span data-ttu-id="c715f-142">Ist der Wert `false` (Standardeinstellung), wird die Ausgabe in der Konsole unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="c715f-142">If `false` (the default), suppresses output to the console.</span></span>|
|`/ShowCallStack`|<span data-ttu-id="c715f-143">Gibt die Aufrufliste in der Protokolldatei aus, wenn im Verlauf der Installation eine Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="c715f-143">Outputs the call stack to the log file if an exception occurs at any point during installation.</span></span>|
|<span data-ttu-id="c715f-144">`/u`[`ninstall`]</span><span class="sxs-lookup"><span data-stu-id="c715f-144">`/u`[`ninstall`]</span></span>|<span data-ttu-id="c715f-145">Deinstalliert die angegebenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c715f-145">Uninstalls the specified assemblies.</span></span> <span data-ttu-id="c715f-146">Im Gegensatz zu den anderen Optionen wird `/u` auf alle Assemblys angewendet, wobei es unerheblich ist, an welcher Stelle in der Befehlszeile sich die Option befindet.</span><span class="sxs-lookup"><span data-stu-id="c715f-146">Unlike the other options, `/u` applies to all assemblies regardless of where the option appears on the command line.</span></span>|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a><span data-ttu-id="c715f-147">Zusätzliche Optionen des Installationsprogramms</span><span class="sxs-lookup"><span data-stu-id="c715f-147">Additional Installer Options</span></span>

<span data-ttu-id="c715f-148">Einzelne Installationsprogramme, die in einer Assembly verwendet werden, erkennen möglicherweise Optionen zusätzlich zu den im Abschnitt [Optionen](#options) aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="c715f-148">Individual installers used within an assembly may recognize options in addition to those listed in the [Options](#options) section.</span></span> <span data-ttu-id="c715f-149">Um Informationen über diese Optionen zu erhalten, führen Sie "InstallUtil.exe" mit den Pfaden der Assemblys in der Befehlszeile zusammen mit der Option `/?` oder `/help` aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-149">To learn about these options, run InstallUtil.exe with the paths of the assemblies on the command line along with the `/?` or `/help` option.</span></span> <span data-ttu-id="c715f-150">Um diese Optionen anzugeben, geben Sie sie in der Befehlszeile zusammen mit den Optionen an, die von "InstallUtil.exe" erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-150">To specify these options, you include them on the command line along with the options recognized by InstallUtil.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="c715f-151">Hilfetext für die Optionen, die von einzelnen Installationsprogrammkomponenten unterstützt werden, wird von der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c715f-151">Help text on the options supported by individual installer components is returned by the <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c715f-152">Auf die einzelnen Optionen, die in der Befehlszeile eingegeben wurden, kann über die <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>-Eigenschaft programmgesteuert zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-152">The individual options that have been entered on the command line are accessible programmatically from the <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="c715f-153">Alle Optionen und Befehlszeilenparameter werden in die Installationsprotokolldatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c715f-153">All options and command-line parameters are written to the installation log file.</span></span> <span data-ttu-id="c715f-154">Wenn Sie jedoch den `/Password`-Parameter verwenden, der von einigen Installationsprogrammkomponenten erkannt wird, werden die Kennwortinformationen durch acht Sternchen (\*) ersetzt und nicht in der Protokolldatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c715f-154">However, if you use the `/Password` parameter, which is recognized by some installer components, the password information will be replaced by eight asterisks (\*) and will not appear in the log file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c715f-155">In einigen Fällen können an das Installationsprogramm übergebene Parameter vertrauliche oder personenbezogene Informationen enthalten, die standardmäßig in eine Nur-Text-Protokolldatei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-155">In some cases, parameters passed to the installer may include sensitive or personally identifiable information, which, by default, is written to a plain text log file.</span></span> <span data-ttu-id="c715f-156">Um dieses Verhalten zu verhindern, können Sie die Protokolldatei unterdrücken, indem Sie `/LogFile=` (ohne *filename*-Argument) nach „Installutil.exe“ in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="c715f-156">To prevent this behavior, you can suppress the log file by specifying `/LogFile=` (with no *filename* argument) after Installutil.exe on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="c715f-157">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c715f-157">Remarks</span></span>

<span data-ttu-id="c715f-158">.NET Framework-Anwendungen bestehen aus herkömmlichen Programmdateien und zugeordneten Ressourcen wie Meldungswarteschlangen, Ereignisprotokollen und Leistungsindikatoren, die beim Bereitstellen der Anwendung erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c715f-158">.NET Framework applications consist of traditional program files and associated resources, such as message queues, event logs, and performance counters that must be created when the application is deployed.</span></span> <span data-ttu-id="c715f-159">Sie können die Installationsprogrammkomponenten einer Assembly verwenden, um diese Ressourcen beim Installieren der Anwendung zu erstellen und beim Deinstallieren der Anwendung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c715f-159">You can use an assembly's installer components to create these resources when your application is installed and to remove them when your application is uninstalled.</span></span> <span data-ttu-id="c715f-160">"Installutil.exe" erkennt diese Installationsprogrammkomponenten und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-160">Installutil.exe detects and executes these installer components.</span></span>

<span data-ttu-id="c715f-161">Sie können mehrere Assemblys in einer Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="c715f-161">You can specify multiple assemblies on the same command line.</span></span> <span data-ttu-id="c715f-162">Jede Option, die vor einem Assemblynamen steht, bezieht sich auf die Installation dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="c715f-162">Any option that occurs before an assembly name applies to that assembly's installation.</span></span> <span data-ttu-id="c715f-163">Mit Ausnahme von `/u` und `/AssemblyName` sind Optionen kumulativ, können jedoch überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-163">Except for `/u` and `/AssemblyName`, options are cumulative but overridable.</span></span> <span data-ttu-id="c715f-164">Das heißt, dass für eine Assembly angegebene Optionen auf alle nachfolgenden Assemblys angewendet werden, es sei denn, die Option wird mit einem neuen Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="c715f-164">That is, options specified for one assembly apply to all subsequent assemblies unless the option is specified with a new value.</span></span>

<span data-ttu-id="c715f-165">Wenn Sie "Installutil.exe" ohne Angabe von Optionen für eine Assembly ausführen, werden die folgenden drei Dateien im Verzeichnis der Assembly platziert:</span><span class="sxs-lookup"><span data-stu-id="c715f-165">If you run Installutil.exe against an assembly without specifying any options, it places the following three files into the assembly's directory:</span></span>

- <span data-ttu-id="c715f-166">"InstallUtil.InstallLog" - Enthält eine allgemeine Beschreibung des Installationsverlaufs.</span><span class="sxs-lookup"><span data-stu-id="c715f-166">InstallUtil.InstallLog - Contains a general description of the installation progress.</span></span>

- <span data-ttu-id="c715f-167">*assemblyname*.InstallLog: Enthält spezielle Informationen, die sich auf die Commitphase des Installationsverlaufs beziehen.</span><span class="sxs-lookup"><span data-stu-id="c715f-167">*assemblyname*.InstallLog - Contains information specific to the commit phase of the installation process.</span></span> <span data-ttu-id="c715f-168">Weitere Informationen zur Commitphase finden Sie in den Informationen zur <xref:System.Configuration.Install.Installer.Commit%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c715f-168">For more information about the commit phase, see the <xref:System.Configuration.Install.Installer.Commit%2A> method.</span></span>

- <span data-ttu-id="c715f-169">*assemblyname*.InstallState: Enthält Daten für die Deinstallation der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c715f-169">*assemblyname*.InstallState - Contains data used to uninstall the assembly.</span></span>

<span data-ttu-id="c715f-170">"Installutil.exe" verwendet Reflektion, um die angegebenen Assemblys zu überprüfen und alle <xref:System.Configuration.Install.Installer>-Typen zu suchen, bei denen das <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType>-Attribut auf `true` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c715f-170">Installutil.exe uses reflection to inspect the specified assemblies and to find all <xref:System.Configuration.Install.Installer> types that have the <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> attribute set to `true`.</span></span> <span data-ttu-id="c715f-171">Anschließend führt das Tool entweder die <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType>- oder die <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType>-Methode für jede Instanz des <xref:System.Configuration.Install.Installer>-Typs aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-171">The tool then executes either the <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> or the <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> method on each instance of the <xref:System.Configuration.Install.Installer> type.</span></span> <span data-ttu-id="c715f-172">"Installutil.exe" führt die Installation in Form einer Transaktion durch. D. h., wenn die Installation einer Assembly fehlschlägt, wird die Installation aller anderen Assemblys zurückgenommen.</span><span class="sxs-lookup"><span data-stu-id="c715f-172">Installutil.exe performs installation in a transactional manner; that is, if one of the assemblies fails to install, it rolls back the installations of all other assemblies.</span></span> <span data-ttu-id="c715f-173">Die Deinstallation wird nicht als Transaktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c715f-173">Uninstall is not transactional.</span></span>

<span data-ttu-id="c715f-174">Verzögert signierte Assemblys können mit "Installutil.exe" weder installiert noch deinstalliert werden, jedoch kann das Tool Assemblys mit starkem Namen installieren und deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c715f-174">Installutil.exe cannot install or uninstall delay-signed assemblies, but it can install or uninstall strong-named assemblies.</span></span>

<span data-ttu-id="c715f-175">Ab .NET Framework, Version 2.0, ist im Lieferumfang der 32-Bit-Version der Common Language Runtime (CLR) ausschließlich die 32-Bit-Version des Installationstools enthalten. Der Lieferumfang der 64-Bit-Version der Common Language Runtime umfasst hingegen sowohl eine 32-Bit-Version als auch eine 64-Bit-Version des Installationstools.</span><span class="sxs-lookup"><span data-stu-id="c715f-175">Starting with the .NET Framework version 2.0, the 32-bit version of the common language runtime (CLR) ships with only the 32-bit version of the Installer tool, but the 64-bit version of the CLR ships with both 32-bit and 64-bit versions of the Installer tool.</span></span> <span data-ttu-id="c715f-176">Verwenden Sie in der 64-Bit-Common Language Runtime zur Installation von 32-Bit-Assemblys das 32-Bit-Installationstool und zur Installation von 64-Bit-Assemblys sowie von Microsoft Intermediate Language (MSIL)-Assemblys das 64-Bit-Installationstool.</span><span class="sxs-lookup"><span data-stu-id="c715f-176">When using the 64-bit CLR, use the 32-bit Installer tool to install 32-bit assemblies, and the 64-bit Installer tool to install 64-bit and Microsoft intermediate language (MSIL) assemblies.</span></span> <span data-ttu-id="c715f-177">Beide Versionen des Installationstools verhalten sich gleich.</span><span class="sxs-lookup"><span data-stu-id="c715f-177">Both versions of the Installer tool behave the same.</span></span>

<span data-ttu-id="c715f-178">Sie können "Installutil.exe" nicht verwenden, um einen Windows-Dienst bereitzustellen, der mit C++ erstellt wurde, da "Installutil.exe" den eingebetteten systemeigenen Code nicht erkennen kann, der vom C++-Compiler erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="c715f-178">You cannot use Installutil.exe to deploy a Windows service that was created by using C++, because Installutil.exe cannot recognize the embedded native code that is produced by the C++ compiler.</span></span> <span data-ttu-id="c715f-179">Wenn Sie versuchen, einen mit C++ erstellten Windows-Dienst mit "Installutil.exe" bereitzustellen, wird eine Ausnahme, z. B. <xref:System.BadImageFormatException>, ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c715f-179">If you try to deploy a C++ Windows service with Installutil.exe, an exception such as <xref:System.BadImageFormatException> will be thrown.</span></span> <span data-ttu-id="c715f-180">Um mit diesem Szenario zu arbeiten, verschieben Sie den Dienstknoten in ein C++-Modul, und schreiben Sie dann das Installationsprogrammobjekt in C# oder Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c715f-180">To work with this scenario, move the service code to a C++ module, and then write the installer object in C# or Visual Basic.</span></span>

## <a name="examples"></a><span data-ttu-id="c715f-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c715f-181">Examples</span></span>

<span data-ttu-id="c715f-182">Mit dem folgenden Befehl werden eine Beschreibung der Befehlssyntax und Optionen für "InstallUtil.exe" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c715f-182">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span>

```console
installutil /?
```

<span data-ttu-id="c715f-183">Mit dem folgenden Befehl werden eine Beschreibung der Befehlssyntax und Optionen für "InstallUtil.exe" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c715f-183">The following command displays a description of the command syntax and options for InstallUtil.exe.</span></span> <span data-ttu-id="c715f-184">Außerdem wird eine Beschreibung und eine Liste der von den Installationsprogrammkomponenten unterstützten Optionen in `myAssembly.exe` angezeigt, wenn Hilfetext der <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>-Eigenschaft des Installationsprogramms zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c715f-184">It also displays a description and list of options supported by the installer components in `myAssembly.exe` if help text has been assigned to the installer's <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> property.</span></span>

```console
installutil /? myAssembly.exe
```

<span data-ttu-id="c715f-185">Der folgende Befehl führt die Installationsprogrammkomponenten in der Assembly `myAssembly.exe` aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-185">The following command executes the installer components in the assembly `myAssembly.exe`.</span></span>

```console
installutil myAssembly.exe
```

<span data-ttu-id="c715f-186">Der folgende Befehl führt die Installationsprogrammkomponenten in einer Assembly mithilfe des `/AssemblyName`-Schalters und eines vollqualifizierten Namens aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-186">The following command executes the installer components in an assembly by using the `/AssemblyName` switch and a fully qualified name.</span></span>

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="c715f-187">Mit dem folgenden Befehl werden die Installationsprogrammkomponenten in einer Assembly, die vom Dateinamen angegeben wird, und in einer Assembly, die mit einem starken Namen angegeben wird, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c715f-187">The following command executes the installer components in an assembly specified by file name and in an assembly specified by strong name.</span></span> <span data-ttu-id="c715f-188">Beachten Sie, dass alle mit Dateinamen angegebenen Assemblys vor Assemblys stehen müssen, die mit starkem Namen in der Befehlszeile angegeben werden, da die `/AssemblyName`-Option nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="c715f-188">Note that all assemblies specified by file name must precede assemblies specified by strong name on the command line, because the `/AssemblyName` option cannot be overridden.</span></span>

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

<span data-ttu-id="c715f-189">Der folgende Befehl führt die Komponenten des Deinstallationsprogramms in der Assembly `myAssembly.exe` aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-189">The following command executes the uninstaller components in the assembly `myAssembly.exe`.</span></span>

```console
installutil /u myAssembly.exe
```

<span data-ttu-id="c715f-190">Der folgende Befehl führt die Komponenten des Deinstallationsprogramms in den Assemblys `myAssembly1.exe` und `myAssembly2.exe` aus.</span><span class="sxs-lookup"><span data-stu-id="c715f-190">The following command executes the uninstaller components in the assemblies `myAssembly1.exe` and `myAssembly2.exe`.</span></span>

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

<span data-ttu-id="c715f-191">Da die Position der `/u`-Option in der Befehlszeile nicht wichtig ist, entspricht diese dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="c715f-191">Because the position of the `/u` option on the command line is not important, this is equivalent to the following command.</span></span>

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

<span data-ttu-id="c715f-192">Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus und gibt an, dass Verlaufsinformationen in `myLog.InstallLog` geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c715f-192">The following command executes the installers in the assembly `myAssembly.exe` and specifies that progress information will be written to `myLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

<span data-ttu-id="c715f-193">Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus, gibt an, dass Statusinformationen in `myLog.InstallLog` geschrieben werden sollen, und verwendet die benutzerdefinierte `/reg`-Option des Installationsprogramms, um anzugeben, dass Updates in der Systemregistrierung vorgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c715f-193">The following command executes the installers in the assembly `myAssembly.exe`, specifies that progress information should be written to `myLog.InstallLog`, and uses the installers' custom `/reg` option to specify that updates should be made to the system registry.</span></span>

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

<span data-ttu-id="c715f-194">Der folgende Befehl führt die Installationsprogramme in der Assembly `myAssembly.exe` aus, verwendet die benutzerdefinierte `/email`-Option des Installationsprogramms zur Angabe der E-Mail-Adresse des Benutzers und unterdrückt die Ausgabe in die Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="c715f-194">The following command executes the installers in the assembly `myAssembly.exe`, uses the installer's custom `/email` option to specify the user's email address, and suppresses output to the log file.</span></span>

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

<span data-ttu-id="c715f-195">Der folgende Befehl schreibt den Installationsverlauf für `myAssembly.exe` in `myLog.InstallLog` und den Verlauf für `myTestAssembly.exe` in `myTestLog.InstallLog`.</span><span class="sxs-lookup"><span data-stu-id="c715f-195">The following command writes the installation progress for `myAssembly.exe` to `myLog.InstallLog` and writes the progress for `myTestAssembly.exe` to `myTestLog.InstallLog`.</span></span>

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a><span data-ttu-id="c715f-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c715f-196">See also</span></span>

- <xref:System.Configuration.Install>
- [<span data-ttu-id="c715f-197">Extras</span><span class="sxs-lookup"><span data-stu-id="c715f-197">Tools</span></span>](index.md)
- [<span data-ttu-id="c715f-198">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="c715f-198">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
