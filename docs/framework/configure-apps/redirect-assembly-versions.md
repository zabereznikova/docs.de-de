---
title: Umleiten von Assemblyversionen
description: Leiten Sie Bindungs Verweise zur Kompilierzeit an verschiedene Versionen von .NET-Assemblys, Assemblys von Drittanbietern oder den Assemblys ihrer eigenen App um.
ms.date: 03/30/2017
helpviewer_keywords:
- assembly binding, redirection
- redirecting assembly binding to earlier version
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], binding redirection
ms.assetid: 88fb1a17-6ac9-4b57-8028-193aec1f727c
ms.openlocfilehash: f0db5c32ba12b8e5313ca363e82260d66a7c010f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166897"
---
# <a name="redirecting-assembly-versions"></a><span data-ttu-id="6d438-103">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="6d438-103">Redirecting Assembly Versions</span></span>

<span data-ttu-id="6d438-104">Sie können Bindungsverweise zu .NET Framework-Assemblys oder Assemblys, die von Drittanbietern oder aus Ihrer eigenen App stammen, zum Zeitpunkt der Kompilierung umleiten.</span><span class="sxs-lookup"><span data-stu-id="6d438-104">You can redirect compile-time binding references to .NET Framework assemblies, third-party assemblies, or your own app's assemblies.</span></span> <span data-ttu-id="6d438-105">Es gibt mehrere Möglichkeiten, eine App so umzuleiten, dass sie eine andere Version einer Assembly verwendet: per Herausgeberrichtlinie, über eine App-Konfigurationsdatei oder mithilfe der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6d438-105">You can redirect your app to use a different version of an assembly in a number of ways: through publisher policy, through an app configuration file; or through the machine configuration file.</span></span> <span data-ttu-id="6d438-106">In diesem Artikel wird erklärt, wie Assemblybindung in .NET Framework funktioniert und wie diese konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d438-106">This article discusses how assembly binding works in the .NET Framework and how it can be configured.</span></span>

<a name="BKMK_Assemblyunificationanddefaultbinding"></a>

## <a name="assembly-unification-and-default-binding"></a><span data-ttu-id="6d438-107">Assemblyvereinheitlichung und Standardbindung</span><span class="sxs-lookup"><span data-stu-id="6d438-107">Assembly unification and default binding</span></span>

 <span data-ttu-id="6d438-108">Bindungen zu .NET Framework-Assemblys werden in einigen Fällen durch einen Prozess umgeleitet, der als *Assemblyvereinheitlichung*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6d438-108">Bindings to .NET Framework assemblies are sometimes redirected through a process called *assembly unification*.</span></span> <span data-ttu-id="6d438-109">.NET Framework besteht aus einer Version der Common Language Runtime und über zwanzig .NET Framework-Assemblys, die die Typbibliothek bilden.</span><span class="sxs-lookup"><span data-stu-id="6d438-109">The .NET Framework consists of a version of the common language runtime and about two dozen .NET Framework assemblies that make up the type library.</span></span> <span data-ttu-id="6d438-110">Diese .NET Framework-Assemblys werden von der Common Language Runtime als abgeschlossene Einheit behandelt.</span><span class="sxs-lookup"><span data-stu-id="6d438-110">These .NET Framework assemblies are treated by the runtime as a single unit.</span></span> <span data-ttu-id="6d438-111">Standardmäßig werden beim Start einer Anwendung alle in von der Runtime ausgeführtem Code enthaltenen Verweise auf Typen zu .NET Framework-Assemblys umgeleitet, die die gleiche Versionsnummer wie die Runtime haben, die in einem Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6d438-111">By default, when an app is launched, all references to types in code run by the runtime are directed to .NET Framework assemblies that have the same version number as the runtime that is loaded in a process.</span></span> <span data-ttu-id="6d438-112">Die bei diesem Modell auftretenden Umleitungen sind das Standardverhalten der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d438-112">The redirections that occur with this model are the default behavior for the runtime.</span></span>

 <span data-ttu-id="6d438-113">Wenn Ihre APP z. b. auf Typen im System.XML-Namespace verweist und mit dem .NET Framework 4,5 erstellt wurde, enthält Sie statische Verweise auf die System.XML Assembly, die mit der Laufzeitversion 4,5 ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="6d438-113">For example, if your app references types in the System.XML namespace and was built by using the .NET Framework 4.5, it contains static references to the System.XML assembly that ships with runtime version 4.5.</span></span> <span data-ttu-id="6d438-114">Wenn Sie den Bindungsverweis so umleiten möchten, dass er auf die System.XML-Assembly aus .NET Framework 4 verweist, können Sie die Informationen bezüglich der Umleitung in der App-Konfigurationsdatei unterbringen.</span><span class="sxs-lookup"><span data-stu-id="6d438-114">If you want to redirect the binding reference to point to the System.XML assembly that ship with the .NET Framework 4, you can put redirect information in the app configuration file.</span></span> <span data-ttu-id="6d438-115">Durch eine Bindungsumleitung in einer Konfigurationsdatei für eine vereinheitlichte .NET Framework-Assembly wird die Vereinheitlichung für diese Assembly abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="6d438-115">A binding redirection in a configuration file for a unified .NET Framework assembly cancels the unification for that assembly.</span></span>

 <span data-ttu-id="6d438-116">Außerdem können Sie eine manuelle Umleitung von Assemblybindungen auch bei Assemblys von Drittanbietern vornehmen, wenn davon mehrere Versionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6d438-116">In addition, you may want to manually redirect assembly binding for third-party assemblies if there are multiple versions available.</span></span>

<a name="BKMK_Redirectingassemblyversionsbyusingpublisherpolicy"></a>

## <a name="redirecting-assembly-versions-by-using-publisher-policy"></a><span data-ttu-id="6d438-117">Umleiten von Assemblyversionen mithilfe der Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6d438-117">Redirecting assembly versions by using publisher policy</span></span>

 <span data-ttu-id="6d438-118">Anbieter von Assemblys können Apps zu einer neueren Version einer Assembly umleiten, indem sie der neuen Assembly eine Herausgeberrichtliniendatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d438-118">Vendors of assemblies can direct apps to a newer version of an assembly by including a publisher policy file with the new assembly.</span></span> <span data-ttu-id="6d438-119">Die Herausgeberrichtliniendatei befindet sich im globalen Assemblycache und enthält Einstellungen für die Umleitung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6d438-119">The publisher policy file, which is located in the global assembly cache, contains assembly redirection settings.</span></span>

 <span data-ttu-id="6d438-120">Jede Version einer Assembly im Format *major*.*minor* verfügt über eine eigene Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="6d438-120">Each *major*.*minor* version of an assembly has its own publisher policy file.</span></span> <span data-ttu-id="6d438-121">So werden zum Beispiel Umleitungen von der Version 2.0.2.222 zu 2.0.3.000 und der Version 2.0.2.321 zu 2.0.3.000 beide in der gleichen Datei eingetragen, da beide zu der gleichen Version 2.0 gehören.</span><span class="sxs-lookup"><span data-stu-id="6d438-121">For example, redirections from version 2.0.2.222 to 2.0.3.000 and from version 2.0.2.321 to version 2.0.3.000 both go into the same file, because they are associated with version 2.0.</span></span> <span data-ttu-id="6d438-122">Eine Umleitung von Version 3.0.0.999 zu 4.0.0.000 müsste jedoch in der Datei für die Version 3.0.999 stehen.</span><span class="sxs-lookup"><span data-stu-id="6d438-122">However, a redirection from version 3.0.0.999 to version 4.0.0.000 goes into the file for version 3.0.999.</span></span> <span data-ttu-id="6d438-123">Jede Hauptversion des .NET Framework verfügt über eine eigene Herausgeberrichtliniendatei.</span><span class="sxs-lookup"><span data-stu-id="6d438-123">Each major version of the .NET Framework has its own publisher policy file.</span></span>

 <span data-ttu-id="6d438-124">Wenn eine Herausgeberrichtliniendatei für eine Assembly vorhanden ist, wird diese nach Prüfung des Assemblymanifests und der App-Konfigurationsdatei von der Runtime überprüft.</span><span class="sxs-lookup"><span data-stu-id="6d438-124">If a publisher policy file exists for an assembly, the runtime checks this file after checking the assembly's manifest and app configuration file.</span></span> <span data-ttu-id="6d438-125">Anbieter sollten Herausgeberrichtlinien nur dann einsetzen, wenn die neue Assembly abwärts kompatibel zu der Assembly ist, die umgeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d438-125">Vendors should use publisher policy files only when the new assembly is backward compatible with the assembly being redirected.</span></span>

 <span data-ttu-id="6d438-126">Sie können die Herausgeberrichtlinie bei Ihrer App umgehen, indem Sie in der App-Konfigurationsdatei Einstellungen angeben, wie im Abschnitt [Umgehen der Herausgeberrichtlinie](#bypass_PP)erläutert.</span><span class="sxs-lookup"><span data-stu-id="6d438-126">You can bypass publisher policy for your app by specifying settings in the app configuration file, as discussed in the [Bypassing publisher policy section](#bypass_PP).</span></span>

<a name="BKMK_Redirectingassemblyversionsattheapplevel"></a>

## <a name="redirecting-assembly-versions-at-the-app-level"></a><span data-ttu-id="6d438-127">Umleiten von Assemblyversionen auf App-Ebene</span><span class="sxs-lookup"><span data-stu-id="6d438-127">Redirecting assembly versions at the app level</span></span>

 <span data-ttu-id="6d438-128">Es gibt verschiedene Techniken, das Bindungsverhalten einer App per App-Konfigurationsdatei zu ändern: Sie können die Datei manuell bearbeiten, sich auf die automatische Bindungsumleitung verlassen oder das Bindungsverhalten unter Umgehung der Herausgeberrichtlinie selbst festlegen.</span><span class="sxs-lookup"><span data-stu-id="6d438-128">There are a few different techniques for changing the binding behavior for your app through the app configuration file: you can manually edit the file, you can rely on automatic binding redirection, or you can specify binding behavior by bypassing publisher policy.</span></span>

### <a name="manually-editing-the-app-config-file"></a><span data-ttu-id="6d438-129">Manuelles Bearbeiten der App-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6d438-129">Manually editing the app config file</span></span>

 <span data-ttu-id="6d438-130">Sie können die App-Konfigurationsdatei manuell bearbeiten, um Assemblyprobleme aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="6d438-130">You can manually edit the app configuration file to resolve assembly issues.</span></span> <span data-ttu-id="6d438-131">Wenn ein Anbieter zum Beispiel eine neuere Assemblyversion veröffentlicht, die von Ihrer App ohne Angabe einer Herausgeberrichtlinie verwendet wird, da diese keine Abwärtskompatibilität garantiert, können Sie die App auf die neuere Version der Assembly umleiten, indem Sie wie folgt Assemblybindungsinformationen in die Konfigurationsdatei eintragen.</span><span class="sxs-lookup"><span data-stu-id="6d438-131">For example, if a vendor might release a newer version of an assembly that your app uses without supplying a publisher policy, because they do not guarantee backward compatibility, you can direct your app to use the newer version of the assembly by putting assembly binding information in your app's configuration file as follows.</span></span>

```xml
<dependentAssembly>
  <assemblyIdentity name="someAssembly"
    publicKeyToken="32ab4ba45e0a69a1"
    culture="en-us" />
  <bindingRedirect oldVersion="7.0.0.0" newVersion="8.0.0.0" />
</dependentAssembly>
```

### <a name="relying-on-automatic-binding-redirection"></a><span data-ttu-id="6d438-132">Nutzen der automatische Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="6d438-132">Relying on automatic binding redirection</span></span>

<span data-ttu-id="6d438-133">Wenn Sie in Visual Studio eine Desktop-App erstellen, die auf den .NET Framework 4.5.1 oder eine höhere Version abzielt, verwendet die APP automatische Bindungs Umleitung.</span><span class="sxs-lookup"><span data-stu-id="6d438-133">When you create a desktop app in Visual Studio that targets the .NET Framework 4.5.1 or a later version, the app uses automatic binding redirection.</span></span> <span data-ttu-id="6d438-134">Das bedeutet Folgendes: Wenn zwei Komponenten auf unterschiedliche Versionen der gleichen Assembly mit starkem Namen verweisen, fügt die Runtime automatisch eine Bindungsumleitung auf die neuere Version der Assembly in der app.config-Ausgabedatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d438-134">This means that if two components reference different versions of the same strong-named assembly, the runtime automatically adds a binding redirection to the newer version of the assembly in the output app configuration (app.config) file.</span></span> <span data-ttu-id="6d438-135">Diese Umleitung überschreibt die Assemblyvereinheitlichung, die sonst erfolgen würde.</span><span class="sxs-lookup"><span data-stu-id="6d438-135">This redirection overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="6d438-136">Die app.config-Quelldatei wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="6d438-136">The source app.config file is not modified.</span></span> <span data-ttu-id="6d438-137">Beispiel: Ihre App verweist direkt auf eine Out-of-Band-.NET Framework-Komponente, verwendet jedoch eine Bibliothek von einem Drittanbieter, die sich auf eine frühere Version der gleichen Komponente bezieht.</span><span class="sxs-lookup"><span data-stu-id="6d438-137">For example, let's say that your app directly references an out-of-band .NET Framework component but uses a third-party library that targets an older version of the same component.</span></span> <span data-ttu-id="6d438-138">Wenn Sie die App kompilieren, wird die app.config-Ausgabedatei so geändert, dass sie eine Umleitung zu der neueren Version der Komponente enthält.</span><span class="sxs-lookup"><span data-stu-id="6d438-138">When you compile the app, the output app configuration file is modified to contain a binding redirection to the newer version of the component.</span></span> <span data-ttu-id="6d438-139">Beim Erstellen einer Web-App erhalten Sie eine Buildwarnung bezüglich des Bindungskonflikts, was Ihnen wiederum die Möglichkeit gibt, der web.config-Quelldatei die erforderliche Bindungsumleitung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d438-139">If you create a web app, you receive a build warning regarding the binding conflict, which in turn, gives you the option to add the necessary binding redirect to the source web configuration file.</span></span>

<span data-ttu-id="6d438-140">Wenn Sie der Quell app.config Datei manuell Bindungs Umleitungen hinzufügen, versucht Visual Studio zum Zeitpunkt der Kompilierung, die Assemblys auf der Grundlage der von Ihnen hinzugefügten Bindungs Umleitungen zu vereinheitlichen.</span><span class="sxs-lookup"><span data-stu-id="6d438-140">If you manually add binding redirects to the source app.config file, at compile time, Visual Studio tries to unify the assemblies based on the binding redirects you added.</span></span> <span data-ttu-id="6d438-141">Wenn Sie zum Beispiel die folgende Bindungsumleitung für eine Assembly einfügen:</span><span class="sxs-lookup"><span data-stu-id="6d438-141">For example, let's say you insert the following binding redirect for an assembly:</span></span>

`<bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0" />`

<span data-ttu-id="6d438-142">Wenn ein anderes Projekt in Ihrer App auf die Version 1.0.0.0 der gleichen Assembly verweist, fügt die automatische Bindungsumleitung den folgende Eintrag zur app.config-Ausgabedatei hinzu, damit die App auf die Version 2.0.0.0 dieser Assemblys vereinheitlicht wird:</span><span class="sxs-lookup"><span data-stu-id="6d438-142">If another project in your app references version 1.0.0.0 of the same assembly, automatic binding redirection adds the following entry to the output app.config file so that the app is unified on version 2.0.0.0 of this assembly:</span></span>

`<bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />`

<span data-ttu-id="6d438-143">Sie können die automatische Bindungs Umleitung aktivieren, wenn Ihre APP auf ältere Versionen der .NET Framework abzielt.</span><span class="sxs-lookup"><span data-stu-id="6d438-143">You can enable automatic binding redirection if your app targets older versions of the .NET Framework.</span></span> <span data-ttu-id="6d438-144">Sie können dieses Standardverhalten überschreiben, indem Sie in der app.config-Datei für jede Assembly Informationen zur Bindungs Umleitung angeben oder indem Sie die Funktion für die Bindungs Umleitung ausschalten.</span><span class="sxs-lookup"><span data-stu-id="6d438-144">You can override this default behavior by providing binding redirection information in the app.config file for any assembly, or by turning off the binding redirection feature.</span></span> <span data-ttu-id="6d438-145">Informationen dazu, wie Sie diese Funktion aktivieren oder deaktivieren, finden Sie unter Gewusst [wie: Aktivieren und Deaktivieren der automatischen Bindungs Umleitung](how-to-enable-and-disable-automatic-binding-redirection.md).</span><span class="sxs-lookup"><span data-stu-id="6d438-145">For information about how to turn this feature on or off, see [How to: Enable and Disable Automatic Binding Redirection](how-to-enable-and-disable-automatic-binding-redirection.md).</span></span>

<a name="bypass_PP"></a>

### <a name="bypassing-publisher-policy"></a><span data-ttu-id="6d438-146">Umgehen der Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6d438-146">Bypassing publisher policy</span></span>

 <span data-ttu-id="6d438-147">Falls erforderlich, können Sie Herausgeberrichtlinien in der App-Konfigurationsdatei überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6d438-147">You can override publisher policy in the app configuration file if necessary.</span></span> <span data-ttu-id="6d438-148">So können zum Beispiel neue Versionen von Assemblys, die als abwärts kompatibel gelten, eine Anwendung trotzdem lahmlegen.</span><span class="sxs-lookup"><span data-stu-id="6d438-148">For example, new versions of assemblies that claim to be backward compatible can still break an app.</span></span> <span data-ttu-id="6d438-149">Wenn Sie die Herausgeber Richtlinie umgehen möchten, fügen Sie [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) dem- [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) Element in der APP-Konfigurationsdatei ein-Element hinzu, und legen Sie das **Apply** -Attribut auf **No**fest, das alle vorherigen **Yes** -Einstellungen überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6d438-149">If you want to bypass publisher policy, add a [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) element to the [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) element in the app configuration file, and set the **apply** attribute to **no**, which overrides any previous **yes** settings.</span></span>

 `<publisherPolicy apply="no" />`

 <span data-ttu-id="6d438-150">Durch das Umgehen der Herausgeberrichtlinie bleibt Ihre App zwar lauffähig, doch sollten Sie dieses Problem auf jeden Fall dem Anbieter der Assembly mitteilen.</span><span class="sxs-lookup"><span data-stu-id="6d438-150">Bypass publisher policy to keep your app running for your users, but make sure you report the problem to the assembly vendor.</span></span> <span data-ttu-id="6d438-151">Wenn eine Assembly über eine Herausgeberrichtliniendatei verfügt, sollte der Anbieter sicherstellen, dass seine Assembly abwärts kompatibel ist und Clients die neue Version in vollem Umfang nutzen können.</span><span class="sxs-lookup"><span data-stu-id="6d438-151">If an assembly has a publisher policy file, the vendor should make sure that the assembly is backward compatible and that clients can use the new version as much as possible.</span></span>

<a name="BKMK_Redirectingassemblyversionsatthemachinelevel"></a>

## <a name="redirecting-assembly-versions-at-the-machine-level"></a><span data-ttu-id="6d438-152">Umleiten von Assemblyversionen auf Computerebene</span><span class="sxs-lookup"><span data-stu-id="6d438-152">Redirecting assembly versions at the machine level</span></span>

 <span data-ttu-id="6d438-153">In seltenen Fällen kann es vorkommen, dass der Administrator möchte, dass sämtliche Apps auf einem Computer eine bestimmte Version einer Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d438-153">There might be rare cases when a machine administrator wants all apps on a computer to use a specific version of an assembly.</span></span> <span data-ttu-id="6d438-154">Das kann zum Beispiel der Fall sein, wenn alle Apps eine bestimmte Version nutzen sollen, weil bei dieser eine Sicherheitslücke geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="6d438-154">For example, the administrator might want every app to use a particular assembly version, because that version fixes a security hole.</span></span> <span data-ttu-id="6d438-155">Wenn eine Assembly in der Konfigurationsdatei des Computers umgeleitet wird, werden alle auf diesem Computer installierten Apps, die bisher die alte Version verwendet haben, zu der neuen Version umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="6d438-155">If an assembly is redirected in the machine's configuration file, all apps on that machine that use the old version will be directed to use the new version.</span></span> <span data-ttu-id="6d438-156">Die Konfigurationsdatei des Computers überschreibt die per App-Konfigurationsdatei und Herausgeberrichtliniendatei getroffenen Festlegungen.</span><span class="sxs-lookup"><span data-stu-id="6d438-156">The machine configuration file overrides the app configuration file and the publisher policy file.</span></span> <span data-ttu-id="6d438-157">Diese Datei befindet sich im Verzeichnis "%*runtime install path*%\Config".</span><span class="sxs-lookup"><span data-stu-id="6d438-157">This file is located in the %*runtime install path*%\Config directory.</span></span> <span data-ttu-id="6d438-158">Das .NET Framework ist meist im Verzeichnis "%drive%\Windows\Microsoft.NET\Framework" installiert.</span><span class="sxs-lookup"><span data-stu-id="6d438-158">Typically, the .NET Framework is installed in the %drive%\Windows\Microsoft.NET\Framework directory.</span></span>

<a name="BKMK_Specifyingassemblybindinginconfigurationfiles"></a>

## <a name="specifying-assembly-binding-in-configuration-files"></a><span data-ttu-id="6d438-159">Angeben der Assemblybindung in Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="6d438-159">Specifying assembly binding in configuration files</span></span>

 <span data-ttu-id="6d438-160">Beim Festlegen von Bindungsumleitungen verwenden Sie in sämtlichen Dateien – in der App-Konfigurationsdatei, der Computer-Konfigurationsdatei oder der Herausgeberrichtliniendatei - das gleiche XML-Format.</span><span class="sxs-lookup"><span data-stu-id="6d438-160">You use the same XML format to specify binding redirects whether it’s in the app configuration file, the machine configuration file, or the publisher policy file.</span></span> <span data-ttu-id="6d438-161">Verwenden Sie das-Element, um eine Assemblyversion zu einer anderen umzuleiten [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) .</span><span class="sxs-lookup"><span data-stu-id="6d438-161">To redirect one assembly version to another, use the [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) element.</span></span> <span data-ttu-id="6d438-162">Mit dem **oldVersion** -Attribut kann sowohl eine einzelne Assemblyversion als auch ein Bereich von Versionen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d438-162">The **oldVersion** attribute can specify a single assembly version or a range of versions.</span></span> <span data-ttu-id="6d438-163">Mit dem `newVersion` -Attribut sollte nur eine einzige Version angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d438-163">The `newVersion` attribute should specify a single version.</span></span>  <span data-ttu-id="6d438-164">Beispielsweise wird durch `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` angegeben, dass die Common Language Runtime die Version 2.0.0.0 statt der Assemblyversionen zwischen 1.1.0.0 und 1.2.0.0 verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="6d438-164">For example, `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` specifies that the runtime should use version 2.0.0.0 instead of the assembly versions between 1.1.0.0 and 1.2.0.0.</span></span>

 <span data-ttu-id="6d438-165">Im folgenden Codebeispiel werden die unterschiedlichsten Szenarien von Bindungsumleitungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d438-165">The following code example demonstrates a variety of binding redirect scenarios.</span></span> <span data-ttu-id="6d438-166">In diesem Beispiel wird für `myAssembly`eine Umleitung für einen Bereich von Versionen und für `mySecondAssembly`eine einzelne Bindungsumleitung angegeben.</span><span class="sxs-lookup"><span data-stu-id="6d438-166">The example specifies a redirect for a range of versions for `myAssembly`, and a single binding redirect for `mySecondAssembly`.</span></span> <span data-ttu-id="6d438-167">Außerdem wird festgelegt, dass die Herausgeberrichtliniendatei nicht die Bindungsumleitungen für `myThirdAssembly`überschreiben soll.</span><span class="sxs-lookup"><span data-stu-id="6d438-167">The example also specifies that publisher policy file will not override the binding redirects for `myThirdAssembly`.</span></span>

 <span data-ttu-id="6d438-168">Zum Binden einer Assembly müssen Sie die Zeichenfolge "urn: Schemas-Microsoft-com: ASM. v1" mit dem **xmlns** -Attribut im- [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) Tag angeben.</span><span class="sxs-lookup"><span data-stu-id="6d438-168">To bind an assembly, you must specify the string "urn:schemas-microsoft-com:asm.v1" with the **xmlns** attribute in the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) tag.</span></span>

```xml
<configuration>
  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <dependentAssembly>
        <assemblyIdentity name="myAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
        <!-- Assembly versions can be redirected in app,
          publisher policy, or machine configuration files. -->
        <bindingRedirect oldVersion="1.0.0.0-2.0.0.0" newVersion="3.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="mySecondAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
             <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
      <assemblyIdentity name="myThirdAssembly"
        publicKeyToken="32ab4ba45e0a69a1"
        culture="en-us" />
        <!-- Publisher policy can be set only in the app
          configuration file. -->
        <publisherPolicy apply="no" />
      </dependentAssembly>
    </assemblyBinding>
  </runtime>
</configuration>
```

### <a name="limiting-assembly--bindings-to-a-specific-version"></a><span data-ttu-id="6d438-169">Einschränken von Assemblybindungen auf eine bestimmte Version</span><span class="sxs-lookup"><span data-stu-id="6d438-169">Limiting assembly  bindings to a specific version</span></span>

 <span data-ttu-id="6d438-170">Mithilfe des **appliesTo** -Attributs für das- [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) Element in einer APP-Konfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version des .NET Framework umleiten.</span><span class="sxs-lookup"><span data-stu-id="6d438-170">You can use the **appliesTo** attribute on the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) element in an app configuration file to redirect assembly binding references to a specific version of the .NET Framework.</span></span> <span data-ttu-id="6d438-171">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d438-171">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="6d438-172">Ohne Angabe eines **appliesTo**-Attributs gilt das [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) -Element für alle Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d438-172">If no **appliesTo** attribute is specified, the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) element applies to all versions of the .NET Framework.</span></span>

 <span data-ttu-id="6d438-173">Um zum Beispiel die Assemblybindung einer .NET Framework 3.5-Assembly umzuleiten, müssten Sie den folgenden XML-Code in die App-Konfigurationsdatei einfügen:</span><span class="sxs-lookup"><span data-stu-id="6d438-173">For example, to redirect assembly binding for a .NET Framework 3.5 assembly, you would include the following XML code in your app configuration file.</span></span>

```xml
<runtime>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1"
    appliesTo="v3.5">
    <dependentAssembly>
      <!-- assembly information goes here -->
    </dependentAssembly>
  </assemblyBinding>
</runtime>
```

 <span data-ttu-id="6d438-174">Die Informationen für Umleitungen sind in Reihenfolge der Versionen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d438-174">You should enter redirection information in version order.</span></span> <span data-ttu-id="6d438-175">So geben Sie beispielsweise erst die Informationen zum Umleiten der Assemblybindung für .NET Framework 3.5-Assemblys und dann die für .NET Framework 4.5-Assemblys ein.</span><span class="sxs-lookup"><span data-stu-id="6d438-175">For example, enter assembly binding redirection information for .NET Framework 3.5 assemblies followed by .NET Framework 4.5 assemblies.</span></span> <span data-ttu-id="6d438-176">Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework-Assemblyumleitungen ein, bei denen nicht das **appliesTo** -Attribut verwendet wird und die daher für alle Versionen .NET Framework-Versionen gelten.</span><span class="sxs-lookup"><span data-stu-id="6d438-176">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="6d438-177">Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d438-177">If there is a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>

 <span data-ttu-id="6d438-178">Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 3.5-Assembly und eines anderen Verweises auf eine .NET Framework 4-Assembly müssten Sie nach dem folgenden Muster vorgehen:</span><span class="sxs-lookup"><span data-stu-id="6d438-178">For example, to redirect one reference to a .NET Framework 3.5 assembly and another reference to a .NET Framework 4 assembly, use the pattern shown in the following pseudocode.</span></span>

```xml
<assemblyBinding xmlns="..." appliesTo="v3.5 ">
  <!--.NET Framework version 3.5 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="..." appliesTo="v4.0.30319">
  <!--.NET Framework version 4.0 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="...">
  <!-- redirects meant for all versions of the runtime -->
</assemblyBinding>
```

## <a name="see-also"></a><span data-ttu-id="6d438-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d438-179">See also</span></span>

- [<span data-ttu-id="6d438-180">How to: Aktivieren und Deaktivieren der Bindungsumleitung</span><span class="sxs-lookup"><span data-stu-id="6d438-180">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="6d438-181">\<bindingRedirect>-Element</span><span class="sxs-lookup"><span data-stu-id="6d438-181">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="6d438-182">Sicherheitsberechtigung für die Umleitung der Assemblybindung</span><span class="sxs-lookup"><span data-stu-id="6d438-182">Assembly Binding Redirection Security Permission</span></span>](assembly-binding-redirection-security-permission.md)
- [<span data-ttu-id="6d438-183">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="6d438-183">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="6d438-184">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="6d438-184">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="6d438-185">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="6d438-185">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6d438-186">Konfigurieren von Apps</span><span class="sxs-lookup"><span data-stu-id="6d438-186">Configuring Apps</span></span>](index.md)
- [<span data-ttu-id="6d438-187">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6d438-187">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="6d438-188">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6d438-188">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="6d438-189">Vorgehensweise: Erstellen einer Herausgeberrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6d438-189">How to: Create a Publisher Policy</span></span>](how-to-create-a-publisher-policy.md)
