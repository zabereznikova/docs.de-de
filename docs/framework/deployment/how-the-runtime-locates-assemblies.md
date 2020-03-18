---
title: So sucht Common Language Runtime nach Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- app.config files, assembly locations
- deploying applications [.NET Framework], assembly locations
- application configuration files, locating assemblies
- .NET Framework application deployment, locating assemblies
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 772ac6f4-64d2-4cfb-92fd-58096dcd6c34
ms.openlocfilehash: 13e2661b67ba3b717b8917e80118175acb09e756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181676"
---
# <a name="how-the-runtime-locates-assemblies"></a>So sucht Common Language Runtime nach Assemblys

Um Ihre .NET Framework-Anwendung erfolgreich bereitstellen zu können, müssen Sie mit dem Verfahren vertraut sein, mit dem die Common Language Runtime die Assemblys sucht und bindet, aus denen Ihre Anwendung zusammengesetzt ist. Standardmäßig versucht die Common Language Runtime, die genaue Version einer Assembly einzubinden, mit der die Anwendung erstellt wurde. Dieses Standardverhalten kann durch Einstellungen in der Konfigurationsdatei überschrieben werden.

Die Common Language Runtime führt eine Reihe von Schritten aus, um eine Assembly zu finden und einen Assemblyverweis aufzulösen. Die einzelnen Schritte werden in den folgenden Abschnitten erläutert. Der Begriff "Überprüfung" wird häufig verwendet, um zu beschreiben, wie die Common Language Runtime nach Assemblys sucht. Er bezieht sich auf die Heuristiken, mit denen die Assembly auf Basis ihres Namens und ihrer Kultur gesucht wird.

> [!NOTE]
> Bindungsinformationen in der Protokolldatei können mit dem [Assembly Binding Log Viewer („Fuslogvw.exe“)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md)angezeigt werden, der im Windows SDK enthalten ist.

## <a name="initiating-the-bind"></a>Initiieren der Bindung

Das Auffinden einer und Binden an eine Assembly beginnt mit dem Versuch der Common Language Runtime, einen Verweis auf eine andere Assembly aufzulösen. Dieser Verweis kann statisch oder dynamisch sein. Der Compiler zeichnet statische Verweise in den Metadaten des Assemblymanifests während der Erstellungszeit auf. Dynamische Verweise werden dynamisch erstellt und resultieren aus dem Aufruf verschiedener Methoden, z. B. <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.

Die bevorzugte Methode zum Verweisen auf eine Assembly ist die Verwendung eines vollständigen Verweises mit Assemblynamen, -version, -kultur und Token des öffentlichen Schlüssels (falls vorhanden). Diese Informationen werden von der Common Language Runtime bei der Suche nach der Assembly verwendet. Die dabei ausgeführten Schritte werden in diesem Abschnitt weiter unten beschrieben. Der von der Common Language Runtime verwendete Auflösungsprozess ist immer gleich, unabhängig davon, ob sich der Verweis auf eine statische oder dynamische Assembly bezieht.

Sie können auch dynamisch auf eine Assembly verweisen, indem Sie die aufrufende Methode nur unter Angabe partieller Informationen zur Assembly, z. B. des Assemblynamens, bereitstellen. In diesem Fall wird lediglich das Anwendungsverzeichnis nach der Assembly durchsucht; es erfolgen keine weiteren Überprüfungen. Einen partiellen Verweis können Sie mit jeder der verschiedenen Methoden zum Laden von Assemblys erstellen, z. B. mit <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>.

Mit einer Methode wie <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> können Sie auch einen dynamischen Verweis erstellen und nur partielle Informationen angeben. Dann qualifizieren Sie den Verweis mithilfe des [\<qualifyAssembly>](../configure-apps/file-schema/runtime/qualifyassembly-element.md)-Elements in der Anwendungskonfigurationsdatei. Mit diesem Element können Sie die vollständigen Verweisinformationen (Name, Version, Kultur und ggf. das Token des öffentlichen Schlüssels) in der Anwendungskonfigurationsdatei statt im Code bereitstellen. Dieses Verfahren sollten Sie anwenden, wenn Sie einen Verweis auf eine Assembly außerhalb des Anwendungsverzeichnisses vollständig qualifizieren oder auf eine Assembly im globalen Assemblycache verweisen möchten, aber gleichzeitig aus praktischen Gründen den vollständigen Verweis in der Konfigurationsdatei statt im Code angeben möchten.

> [!NOTE]
> Diesen Typ des partiellen Verweises sollten Sie nicht bei Assemblys verwenden, die für mehrere Anwendungen freigegeben sind. Da Konfigurationseinstellungen nach Anwendung und nicht nach Assembly erfolgen, müssten bei einer freigegebenen Assembly mit diesem Typ des partiellen Verweises für jede Anwendung, die diese freigegebene Assembly verwendet, die qualifizierenden Informationen in der jeweiligen Konfigurationsdatei enthalten sein.

Die Common Language Runtime verwendet die folgenden Schritte, um einen Assemblyverweis aufzulösen:

1. [Bestimmen der korrekten Assemblyversion](#step1) durch Überprüfung anwendbarer Konfigurationsdateien, einschließlich der Anwendungskonfigurationsdatei, der Herausgeberrichtliniendatei und der Computerkonfigurationsdatei. Wenn die Konfigurationsdatei auf einem Remotecomputer gespeichert ist, muss die Common Language Runtime zuerst die Anwendungskonfigurationsdatei suchen und herunterladen.

2. [Überprüfen, ob der Assemblyname bereits zuvor gebunden wurde](#step2) . Ist dies der Fall, wird die zuvor geladene Assembly verwendet. Wenn eine vorherige Anforderung zum Laden der Assembly nicht ausgeführt werden konnte, führt die Anforderung sofort zu einem Fehler, ohne dass versucht wird, die Assembly zu laden.

    > [!NOTE]
    > Das Caching von Assemblybindungsfehlern ist neu in .NET Framework Version 2.0.

3. [Durchsuchen des globalen Assemblycache](#step3). Wird die Assembly dort gefunden, wird sie von der Common Language Runtime verwendet.

4. [Suchen der Assembly](#step4) , wobei folgendermaßen vorgegangen wird:

    1. Wenn die Konfiguration und die Herausgeberrichtlinie keine Auswirkung auf den ursprünglichen Verweis haben und die Anforderung zur Bindung mithilfe der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> -Methode erstellt wurde, sucht die Common Language Runtime nach Hinweisen auf den Speicherort.

    2. Wenn eine CodeBase in den Konfigurationsdateien gefunden wurde, wird nur dieser Speicherort überprüft. Wenn die Überprüfung fehlschlägt, wird durch die Common Language Runtime festgelegt, dass die Anforderung zur Bindung fehlgeschlagen ist und keine weitere Überprüfung erfolgt.

    3. Überprüfen der Assembly mithilfe von Heuristiken, die im Abschnitt [Überprüfung](#step4)beschrieben sind. Wurde die Assembly nach der Überprüfung nicht gefunden, fordert die Common Language Runtime Windows Installer auf, die Assembly zur Verfügung zu stellen. Dabei handelt es sich um eine Installation bei Bedarf.

        > [!NOTE]
        > Es findet weder eine Versionsüberprüfung von Assemblys ohne starken Namen statt, noch überprüft die Common Language Runtime den globalen Assemblycache nach Assemblys ohne starken Namen.

<a name="step1"></a>

## <a name="step-1-examining-the-configuration-files"></a>Schritt 1: Untersuchen der Konfigurationsdateien

Das Assemblybindungsverhalten kann auf verschiedenen Ebenen auf Basis von drei XML-Dateien konfiguriert werden:

- Anwendungskonfigurationsdatei

- Herausgeberrichtliniendatei

- Computerkonfigurationsdatei

Diese Dateien verwenden dieselbe Syntax und stellen Informationen wie Bindungsumleitungen, den Speicherort des Codes und Bindungsarten für bestimmte Assemblys zur Verfügung. Jede Konfigurationsdatei kann ein [\<assemblyBinding>-Element](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) enthalten, das den Bindungsprozess umleitet. Die untergeordneten Elemente des [\<assemblyBinding>-Elements](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) enthalten das [\<dependentAssembly>-Element](../configure-apps/file-schema/runtime/dependentassembly-element.md). Die untergeordneten Elemente des [\<dependentAssembly>-Elements](../configure-apps/file-schema/runtime/dependentassembly-element.md) schließen das [\<assemblyIdentity>-Element](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment), das [\<bindingRedirect>-Element](../configure-apps/file-schema/runtime/bindingredirect-element.md) und das [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) ein.

> [!NOTE]
> Konfigurationsinformationen sind in den drei Konfigurationsdateien enthalten. Nicht alle Elemente sind auch in allen Konfigurationsdateien gültig. So können sich z. B. Informationen zum Bindungsmodus und privaten Pfad nur in der Anwendungskonfigurationsdatei befinden. Eine vollständige Liste der Informationen, die in jeder Datei enthalten sind, finden Sie unter [Konfigurieren von Apps mithilfe von Konfigurationsdateien](../configure-apps/index.md).

### <a name="application-configuration-file"></a>Anwendungskonfigurationsdatei

Im ersten Schritt durchsucht die Common Language Runtime die Anwendungskonfigurationsdatei nach Informationen, die die im Manifest der aufrufenden Assembly gespeicherten Versionsinformationen überschreiben. Die Anwendungskonfigurationsdatei kann mit einer Anwendung bereitgestellt werden, wird aber nicht für die Ausführung der Anwendung benötigt. In der Regel erfolgt der Abruf dieser Datei fast unmittelbar, aber in Fällen, in denen sich die Anwendungsbasis auf einem Remotecomputer befindet, wie z. B. in einem webbasierten Szenario mit Internet Explorer, muss die Konfigurationsdatei heruntergeladen werden.

Im Fall von ausführbaren Clientdateien befindet sich die Anwendungskonfigurationsdatei im selben Verzeichnis wie die ausführbare Datei der Anwendung und verfügt über denselben Basisnamen wie diese sowie über die Dateierweiterung ".config". Die Konfigurationsdatei für "C:\Programme\Myapp\Myapp.exe" ist beispielsweise "C:\Programme\Myapp\Myapp.exe.config". In einem browserbasierten Szenario muss die HTML-Datei das **\<link>** -Element verwenden, um explizit auf die Konfigurationsdatei zu verweisen.

Der folgende Code bietet ein einfaches Beispiel für eine Anwendungskonfigurationsdatei. In diesem Beispiel wird der <xref:System.Diagnostics.TextWriterTraceListener> -Auflistung ein <xref:System.Diagnostics.Debug.Listeners%2A> hinzugefügt, um das Aufzeichnen von Debuginformationen in einer Datei zu aktivieren.

```xml
<configuration>
   <system.diagnostics>
      <trace useGlobalLock="false" autoflush="true" indentsize="0">
         <listeners>
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />
         </listeners>
      </trace>
   </system.diagnostics>
</configuration>
```

### <a name="publisher-policy-file"></a>Herausgeberrichtliniendatei

Im zweiten Schritt überprüft die Common Language Runtime die Herausgeberrichtliniendatei, sofern eine solche vorhanden ist. Herausgeberrichtliniendateien werden von einem Komponentenherausgeber als Fix oder Update an eine freigegebene Komponente verteilt. Diese Dateien enthalten Informationen zur Kompatibilität, die vom Herausgeber der freigegebenen Komponente ausgegeben werden. Diese Komponente leitet einen Assemblyverweis an eine neue Version weiter. Anders als Anwendungs- und Computerkonfigurationsdateien sind Herausgeberrichtliniendateien in ihren eigenen Assemblys enthalten, die im globalen Assemblycache installiert sein müssen.

Es folgt ein Beispiel einer Konfigurationsdatei für Herausgeberrichtlinien:

```xml
<configuration>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">

            <dependentAssembly>
                <assemblyIdentity name="asm6" publicKeyToken="c0305c36380ba429" />
                <bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0"/>
            </dependentAssembly>

        </assemblyBinding>
    </runtime>
</configuration>
```

Zum Erstellen einer Assembly können Sie das [Al.exe (Assembly Linker)](../tools/al-exe-assembly-linker.md)-Tool mit einem Befehl wie dem Folgenden verwenden:

```console
Al.exe /link:asm6.exe.config /out:policy.3.0.asm6.dll /keyfile: compatkey.dat /v:3.0.0.0
```

`compatkey.dat` ist eine Schlüsseldatei mit starkem Namen. Dieser Befehl erstellt eine Assembly mit starkem Namen, die Sie im globalen Assemblycache einfügen können.

> [!NOTE]
> Herausgeberrichtlinien haben Auswirkungen auf alle Anwendungen, die eine freigegebene Komponente verwenden.

Die Konfigurationsdatei für Herausgeberrichtlinien überschreibt Versionsinformationen, die aus der Anwendung stammen (d. h. aus dem Assemblymanifest oder aus der Anwendungskonfigurationsdatei). Wenn in der Anwendungskonfigurationsdatei keine Anweisung zur Umleitung der im Assemblymanifest angegebenen Version enthalten ist, überschreibt die Herausgeberrichtliniendatei die Version, die im Assemblymanifest angeben ist. Enthält die Anwendungskonfigurationsdatei hingegen eine Umleitungsanweisung, überschreibt die Herausgeberrichtlinie die dort angegebene Version und nicht diejenige, die im Manifest angegeben ist.

Eine Herausgeberrichtliniendatei wird verwendet, wenn eine freigegebene Komponente aktualisiert wird und die neue Version der freigegebenen Komponente von allen Anwendungen übernommen werden soll, die diese Komponente verwenden. Die Einstellungen in der Herausgeberrichtliniendatei überschreiben diejenigen der Anwendungskonfigurationsdatei, es sei denn, diese erzwingt den abgesicherten Modus.

#### <a name="safe-mode"></a>Abgesicherter Modus
Herausgeberrichtliniendateien werden in der Regel explizit als Teil eines Service Packs oder eines Programmupdates installiert. Wenn Probleme mit der aktualisierten freigegebenen Komponente auftreten sollten, können Sie die Überschreibungen in der Herausgeberrichtliniendatei ignorieren und den abgesicherten Modus verwenden. Der abgesicherte Modus wird vom Element **\<publisherPolicy apply="yes**&#124;**no"/>** bestimmt, das sich nur in der Anwendungskonfigurationsdatei befindet. Es legt fest, ob die Informationen zur Herausgeberrichtlinienkonfiguration aus dem Bindungsprozess entfernt werden sollten.

Der abgesicherte Modus kann auf die gesamte Anwendung oder ausgewählte Assemblys angewendet werden. Das heißt, Sie können die Richtlinie für alle Assemblys aufheben, aus denen die Anwendung zusammengesetzt ist, oder für einige ausgewählte Assemblys aktivieren. Um die Herausgeberrichtlinie selektiv auf Assemblys anzuwenden, aus denen sich eine Anwendung zusammensetzt, legen Sie **\<publisherPolicy apply\=no/>** fest und bestimmen die Assemblys, die davon betroffen sein sollen, mit dem \<**dependentAssembly**>-Element. Um die Herausgeberrichtlinie auf alle Assemblys anzuwenden, legen Sie **\<publisherPolicy apply\=no/>** ohne abhängige Assemblyelemente fest. Weitere Informationen zur Konfiguration finden Sie unter [Konfigurieren von Apps mithilfe von Konfigurationsdateien](../configure-apps/index.md).

### <a name="machine-configuration-file"></a>Computerkonfigurationsdatei
Im dritten Schritt überprüft die Common Language Runtime die Computerkonfigurationsdatei. Diese Datei mit dem Namen "Machine.config" befindet sich auf dem lokalen Computer im Unterverzeichnis "Config" des Stammverzeichnisses, in dem die Common Language Runtime installiert ist. Diese Datei kann von Administratoren verwendet werden, um lokale Assemblybindungsbeschränkungen für diesen Computer festzulegen. Die Einstellungen in der Computerkonfigurationsdatei haben Vorrang vor allen anderen Konfigurationseinstellungen. Dies bedeutet allerdings nicht, dass sich alle Konfigurationseinstellungen in dieser Datei befinden sollten. Die Version, die in der Administratorrichtliniendatei festgelegt ist, ist endgültig und kann nicht überschrieben werden. Überschreibungen, die in der Datei "Machine.config" festgelegt sind, haben Auswirkungen auf alle Anwendungen. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurieren von Apps mithilfe von Konfigurationsdateien](../configure-apps/index.md).

<a name="step2"></a>

## <a name="step-2-checking-for-previously-referenced-assemblies"></a>Schritt 2: Suchen nach Assemblys, auf die zuvor verwiesen wurde

Wenn die angeforderte Assembly bereits in vorherigen Aufrufen angefordert wurde, verwendet die Common Language Runtime die Assembly, die bereits geladen ist. Dies kann sich auf die Namensgebung für Assemblys auswirken, aus denen eine Anwendung zusammengesetzt ist. Weitere Informationen zum Benennen von Assemblys finden Sie unter [Assemblynamen](../../standard/assembly/names.md).

Wenn eine vorherige Anforderung für die Assembly nicht ausgeführt werden konnte, führen weitere Anforderungen sofort zu einem Fehler, ohne dass versucht wird, die Assembly zu laden. Ab .NET Framework Version 2.0 werden Assemblybindungsfehler zwischengespeichert. Anhand der zwischengespeicherten Informationen wird bestimmt, ob versucht wird, die Assembly zu laden.

> [!NOTE]
> Um zu dem Verhalten der .NET Framework-Versionen 1.0 und 1.1 zurückzukehren, in denen Bindungsfehler nicht zwischengespeichert wurden, nehmen Sie das [\<disableCachingBindingFailures>-Element](../configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md) in Ihre Konfigurationsdatei auf.

<a name="step3"></a>

## <a name="step-3-checking-the-global-assembly-cache"></a>Schritt 3: Durchsuchen des globalen Assemblycache

Für Assemblys mit starkem Namen wird der Bindungsprozess durch die Überprüfung des globalen Assemblycache fortgesetzt. Im globalen Assemblycache werden Assemblys gespeichert, die von mehreren Anwendungen auf einem Computer verwendet werden können. Alle Assemblys im globalen Assemblycache müssen einen starken Namen aufweisen.

<a name="step4"></a>

## <a name="step-4-locating-the-assembly-through-codebases-or-probing"></a>Schritt 4: Suchen der Assembly mit CodeBases oder durch Überprüfung

Nachdem die richtige Assemblyversion mithilfe der Informationen aus dem Verweis der aufrufenden Assembly und den Konfigurationsdateien ermittelt worden ist und der globale Assemblycache (nur nach Assemblys mit starkem Namen) überprüft wurde, versucht die Common Language Runtime, die Assembly ausfindig zu machen. Die Suche nach einer Assembly setzt sich aus folgenden Schritten zusammen:

1. Wird ein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element in der Anwendungskonfigurationsdatei gefunden, überprüft die Common Language Runtime den angegebenen Speicherort. Wenn eine Übereinstimmung gefunden wird, wird diese Assembly verwendet und es findet keine Überprüfung statt. Wird die Assembly dort nicht gefunden, schlägt die Bindungsanforderung fehl.

2. Die Common Language Runtime sucht daraufhin nach der Assembly, auf die verwiesen wurde, und wendet dabei die Regeln an, die weiter unten im Abschnitt erläutert sind.

> [!NOTE]
> Wenn mehrere Versionen einer Assembly in einem Verzeichnis vorhanden sind und Sie auf eine bestimmte Version dieser Assembly verweisen möchten, müssen Sie das [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element anstelle des `privatePath`-Attributs des [\<probing>](../configure-apps/file-schema/runtime/probing-element.md)-Elements verwenden. Bei Verwendung des [\<probing>](../configure-apps/file-schema/runtime/probing-element.md)-Elements beendet die Common Language Runtime die Überprüfung beim ersten Auffinden einer Assembly mit dem einfachen Assemblynamen, auf den verwiesen wird, ganz gleich, ob es sich um eine korrekte Übereinstimmung handelt oder nicht. Bei einer korrekten Übereinstimmung wird diese Assembly verwendet. Wenn es sich nicht um eine korrekte Übereinstimmung handelt, wird die Überprüfung beendet und die Bindung schlägt fehl.

### <a name="locating-the-assembly-through-codebases"></a>Assemblysuche mit CodeBases

CodeBase-Informationen können über ein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element in einer Konfigurationsdatei zur Verfügung gestellt werden. Diese CodeBase wird stets überprüft, bevor die Common Language Runtime nach der Assembly sucht, auf die verwiesen wird. Enthält eine Herausgeberrichtliniendatei, in der die Umleitung der endgültigen Version enthalten ist, auch ein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element, wird dieses [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element verwendet. Wenn beispielsweise Ihre Anwendungskonfigurationsdatei ein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element festlegt, gleichzeitig aber eine Herausgeberrichtliniendatei, die Anwendungsinformationen überschreibt, ebenfalls ein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element festlegt, wird das [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element in der Herausgeberrichtliniendatei verwendet.

Wenn am Speicherort, der durch das [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element angegeben ist, keine Übereinstimmung gefunden wird, schlägt die Bindungsanforderung fehl und es werden keine weiteren Schritte ausgeführt. Wird durch die Common Language Runtime ermittelt, dass eine Assembly den Kriterien der aufrufenden Assembly entspricht, wird diese Assembly verwendet. Wenn die durch das angegebene [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element festgelegte Datei geladen wird, überprüft die Common Language Runtime, ob Name, Version, Kultur und öffentlicher Schlüssel dem Verweis der aufrufenden Assembly entsprechen.

> [!NOTE]
> Assemblys, auf die verwiesen wird und die sich außerhalb des Stammverzeichnisses der Anwendung befinden, müssen einen starken Namen aufweisen und entweder im globalen Assemblycache installiert sein oder mithilfe des [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Elements angegeben werden.

### <a name="locating-the-assembly-through-probing"></a>Assemblysuche durch Überprüfung

Wenn sich kein [\<codeBase>](../configure-apps/file-schema/runtime/codebase-element.md)-Element in der Anwendungskonfigurationsdatei befindet, führt die Common Language Runtime eine Überprüfung für die Assembly anhand von vier Kriterien durch:

- Anwendungsbasis, die der Stammort für die Ausführung der Anwendung ist.

- Kultur, die das Kulturattribut der Assembly darstellt, auf die verwiesen wird.

- Name der Assembly, auf die verwiesen wird.

- Das `privatePath`-Attribut des [\<probing>](../configure-apps/file-schema/runtime/probing-element.md)-Elements, bei dem es sich um die benutzerdefinierte Liste von Unterverzeichnissen unter dem Stammspeicherort handelt. Dieser Speicherort kann in der Anwendungskonfigurationsdatei und in verwaltetem Code mithilfe der <xref:System.AppDomainSetup.PrivateBinPath?displayProperty=nameWithType>-Eigenschaft für eine Anwendungsdomäne festgelegt werden. Im Fall der Festlegung in verwaltetem Code wird zuerst der `privatePath` des verwalteten Codes und daraufhin der in der Anwendungskonfigurationsdatei angegebene Pfad überprüft.

#### <a name="probing-the-application-base-and-culture-directories"></a>Überprüfen der Anwendungsbasis- und Kulturverzeichnisse

Die Common Language Runtime beginnt mit der Überprüfung immer in der Anwendungsbasis, die entweder eine URL oder das Stammverzeichnis der Anwendung auf einem Computer ist. Wird die Assembly, auf die verwiesen wird, in der Anwendungsbasis nicht gefunden und stehen keine Informationen zur Kultur bereit, durchsucht die Common Language Runtime alle Unterverzeichnisse mit diesem Assemblynamen. Zu den überprüften Verzeichnissen gehören:

- [Anwendungsbasis] / [Assemblyname].dll

- [Anwendungsbasis] / [Assemblyname] / [Assemblyname].dll

Wenn für die Assembly, auf die verwiesen wird, Informationen zur Kultur angegeben sind, werden nur die folgenden Verzeichnisse überprüft:

- [Anwendungsbasis] / [Kultur] / [Assemblyname].dll

- [Anwendungsbasis] / [Kultur] / [Assemblyname] / [Assemblyname].dll

#### <a name="probing-with-the-privatepath-attribute"></a>Überprüfen mit dem privatePath-Attribut

Zusätzlich zu den Unterverzeichnissen der Kultur und den Unterverzeichnissen mit dem Namen der Assembly, auf die verwiesen wird, überprüft die Common Language Runtime auch Verzeichnisse, die mit dem `privatePath`-Attribut des [\<probing>](../configure-apps/file-schema/runtime/probing-element.md)-Elements angegeben werden. Die Verzeichnisse, die mit dem `privatePath` -Attribut angegeben werden, müssen Unterverzeichnisse des Stammverzeichnisses der Anwendung sein. Die überprüften Verzeichnisse unterscheiden sich, je nachdem, ob Informationen zur Kultur in der Anforderung der Assembly enthalten sind, auf die verwiesen wird.

Die Common Language Runtime beendet die Überprüfung beim ersten Auffinden einer Assembly mit dem einfachen Assemblynamen, auf den verwiesen wird, ganz gleich, ob es sich um eine korrekte Übereinstimmung handelt oder nicht. Bei einer korrekten Übereinstimmung wird diese Assembly verwendet. Wenn es sich nicht um eine korrekte Übereinstimmung handelt, wird die Überprüfung beendet und die Bindung schlägt fehl.

Wenn Informationen zur Kultur enthalten sind, erfolgt die Überprüfung der folgenden Verzeichnisse:

- [Anwendungsbasis] / [bin-Pfad] / [Kultur] / [Assemblyname].dll

- [Anwendungsbasis] / [bin-Pfad] / [Kultur] / [Assemblyname] / [Assemblyname].dll

Wenn keine Informationen zur Kultur enthalten sind, werden die folgenden Verzeichnisse überprüft:

- [Anwendungsbasis] / [bin-Pfad] / [Assemblyname].dll

- [Anwendungsbasis] / [bin-Pfad] / [Assemblyname] / [Assemblyname].dll

#### <a name="probing-examples"></a>Beispiele einer Überprüfung

Folgende Informationen stehen zur Verfügung:

- Name der Assembly, auf die verwiesen wird: myAssembly

- Webanwendungs-Stammverzeichnis: `http://www.code.microsoft.com`

- [\<probing>](../configure-apps/file-schema/runtime/probing-element.md)-Element in der Konfigurationsdatei: bin

- Kultur: de

Die Common Language Runtime überprüft die folgenden URLs:

- `http://www.code.microsoft.com/de/myAssembly.dll`

- `http://www.code.microsoft.com/de/myAssembly/myAssembly.dll`

- `http://www.code.microsoft.com/bin/de/myAssembly.dll`

- `http://www.code.microsoft.com/bin/de/myAssembly/myAssembly.dll`

##### <a name="multiple-assemblies-with-the-same-name"></a>Mehrere Assemblys mit dem gleichen Namen

Das folgende Beispiel zeigt, wie mehrere Assemblys mit dem gleichen Namen konfiguriert werden.

```xml
<dependentAssembly>
   <assemblyIdentity name="Server" publicKeyToken="c0305c36380ba429" />
   <codeBase version="1.0.0.0" href="v1/Server.dll" />
   <codeBase version="2.0.0.0" href="v2/Server.dll" />
</dependentAssembly>
```

#### <a name="other-locations-probed"></a>Weitere überprüfte Speicherorte

Der Speicherort einer Assembly kann auch mithilfe des aktuellen Bindungskontexts ermittelt werden. Dieses Verfahren kommt besonders häufig bei Verwendung der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> -Methode und in Szenarien mit COM-Interop zum Einsatz. Wenn eine Assembly die <xref:System.Reflection.Assembly.LoadFrom%2A> -Methode verwendet, um auf eine andere Assembly zu verweisen, wird der Speicherort der aufrufenden Assembly als Hinweis auf den Speicherort der Assembly angesehen, auf die verwiesen wird. Bei gefundener Übereinstimmung wird diese Assembly geladen. Besteht keine Übereinstimmung, setzt die Common Language Runtime die Suche mit der entsprechenden Semantik fort und fordert Windows Installer auf, die Assembly zur Verfügung zu stellen. Wenn keine Assembly zur Verfügung gestellt wird, die mit der Bindungsanforderung übereinstimmt, wird eine Ausnahme ausgelöst. Bei der Ausnahme handelt es sich um eine <xref:System.TypeLoadException> in verwaltetem Code, sofern auf einen Typ verwiesen wurde, oder um eine <xref:System.IO.FileNotFoundException> , sofern die geladene Assembly nicht gefunden wurde.

Wenn beispielsweise „Assembly1“ auf „Assembly2“ verweist und „Assembly1“ von `http://www.code.microsoft.com/utils` heruntergeladen wurde, wird dieser Speicherort als Hinweis auf den Speicherort von „Assembly2.dll“ angesehen. Die Runtime sucht in `http://www.code.microsoft.com/utils/Assembly2.dll` und `http://www.code.microsoft.com/utils/Assembly2/Assembly2.dll` nach der Assembly. Wenn "Assembly2" in keinem der beiden Speicherorte vorhanden ist, wird eine Anfrage an Windows Installer gestellt.

## <a name="see-also"></a>Siehe auch

- [Bewährte Methoden für das Laden von Assemblys](best-practices-for-assembly-loading.md)
- [Bereitstellung](index.md)
