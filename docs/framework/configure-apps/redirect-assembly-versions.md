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
ms.openlocfilehash: 4cfd4336fb9999c996bea28eb86f1143932d4c51
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141733"
---
# <a name="redirecting-assembly-versions"></a>Umleiten von Assemblyversionen

Sie können Bindungsverweise zu .NET Framework-Assemblys oder Assemblys, die von Drittanbietern oder aus Ihrer eigenen App stammen, zum Zeitpunkt der Kompilierung umleiten. Es gibt mehrere Möglichkeiten, eine App so umzuleiten, dass sie eine andere Version einer Assembly verwendet: per Herausgeberrichtlinie, über eine App-Konfigurationsdatei oder mithilfe der Computerkonfigurationsdatei. In diesem Artikel wird erklärt, wie Assemblybindung in .NET Framework funktioniert und wie diese konfiguriert werden kann.

<a name="BKMK_Assemblyunificationanddefaultbinding"></a>
## <a name="assembly-unification-and-default-binding"></a>Assemblyvereinheitlichung und Standardbindung
 Bindungen zu .NET Framework-Assemblys werden in einigen Fällen durch einen Prozess umgeleitet, der als *Assemblyvereinheitlichung*bezeichnet wird. .NET Framework besteht aus einer Version der Common Language Runtime und über zwanzig .NET Framework-Assemblys, die die Typbibliothek bilden. Diese .NET Framework-Assemblys werden von der Common Language Runtime als abgeschlossene Einheit behandelt. Standardmäßig werden beim Start einer Anwendung alle in von der Runtime ausgeführtem Code enthaltenen Verweise auf Typen zu .NET Framework-Assemblys umgeleitet, die die gleiche Versionsnummer wie die Runtime haben, die in einem Prozess geladen wird. Die bei diesem Modell auftretenden Umleitungen sind das Standardverhalten der Common Language Runtime.

 Wenn Ihre APP z. b. auf Typen im System.XML-Namespace verweist und mit dem .NET Framework 4,5 erstellt wurde, enthält Sie statische Verweise auf die System.XML Assembly, die mit der Laufzeitversion 4,5 ausgeliefert wird. Wenn Sie den Bindungsverweis so umleiten möchten, dass er auf die System.XML-Assembly aus .NET Framework 4 verweist, können Sie die Informationen bezüglich der Umleitung in der App-Konfigurationsdatei unterbringen. Durch eine Bindungsumleitung in einer Konfigurationsdatei für eine vereinheitlichte .NET Framework-Assembly wird die Vereinheitlichung für diese Assembly abgebrochen.

 Außerdem können Sie eine manuelle Umleitung von Assemblybindungen auch bei Assemblys von Drittanbietern vornehmen, wenn davon mehrere Versionen verfügbar sind.

<a name="BKMK_Redirectingassemblyversionsbyusingpublisherpolicy"></a>
## <a name="redirecting-assembly-versions-by-using-publisher-policy"></a>Umleiten von Assemblyversionen mithilfe der Herausgeberrichtlinie
 Anbieter von Assemblys können Apps zu einer neueren Version einer Assembly umleiten, indem sie der neuen Assembly eine Herausgeberrichtliniendatei hinzufügen. Die Herausgeberrichtliniendatei befindet sich im globalen Assemblycache und enthält Einstellungen für die Umleitung der Assembly.

 Jede Version einer Assembly im Format *major*.*minor* verfügt über eine eigene Herausgeberrichtliniendatei. So werden zum Beispiel Umleitungen von der Version 2.0.2.222 zu 2.0.3.000 und der Version 2.0.2.321 zu 2.0.3.000 beide in der gleichen Datei eingetragen, da beide zu der gleichen Version 2.0 gehören. Eine Umleitung von Version 3.0.0.999 zu 4.0.0.000 müsste jedoch in der Datei für die Version 3.0.999 stehen. Jede Hauptversion des .NET Framework verfügt über eine eigene Herausgeberrichtliniendatei.

 Wenn eine Herausgeberrichtliniendatei für eine Assembly vorhanden ist, wird diese nach Prüfung des Assemblymanifests und der App-Konfigurationsdatei von der Runtime überprüft. Anbieter sollten Herausgeberrichtlinien nur dann einsetzen, wenn die neue Assembly abwärts kompatibel zu der Assembly ist, die umgeleitet werden soll.

 Sie können die Herausgeberrichtlinie bei Ihrer App umgehen, indem Sie in der App-Konfigurationsdatei Einstellungen angeben, wie im Abschnitt [Umgehen der Herausgeberrichtlinie](#bypass_PP)erläutert.

<a name="BKMK_Redirectingassemblyversionsattheapplevel"></a>
## <a name="redirecting-assembly-versions-at-the-app-level"></a>Umleiten von Assemblyversionen auf App-Ebene
 Es gibt verschiedene Techniken, das Bindungsverhalten einer App per App-Konfigurationsdatei zu ändern: Sie können die Datei manuell bearbeiten, sich auf die automatische Bindungsumleitung verlassen oder das Bindungsverhalten unter Umgehung der Herausgeberrichtlinie selbst festlegen.

### <a name="manually-editing-the-app-config-file"></a>Manuelles Bearbeiten der App-Konfigurationsdatei
 Sie können die App-Konfigurationsdatei manuell bearbeiten, um Assemblyprobleme aufzulösen. Wenn ein Anbieter zum Beispiel eine neuere Assemblyversion veröffentlicht, die von Ihrer App ohne Angabe einer Herausgeberrichtlinie verwendet wird, da diese keine Abwärtskompatibilität garantiert, können Sie die App auf die neuere Version der Assembly umleiten, indem Sie wie folgt Assemblybindungsinformationen in die Konfigurationsdatei eintragen.

```xml
<dependentAssembly>
  <assemblyIdentity name="someAssembly"
    publicKeyToken="32ab4ba45e0a69a1"
    culture="en-us" />
  <bindingRedirect oldVersion="7.0.0.0" newVersion="8.0.0.0" />
</dependentAssembly>
```

### <a name="relying-on-automatic-binding-redirection"></a>Nutzen der automatische Bindungsumleitung

Wenn Sie in Visual Studio eine Desktop-App erstellen, die auf den .NET Framework 4.5.1 oder eine höhere Version abzielt, verwendet die APP automatische Bindungs Umleitung. Das bedeutet Folgendes: Wenn zwei Komponenten auf unterschiedliche Versionen der gleichen Assembly mit starkem Namen verweisen, fügt die Runtime automatisch eine Bindungsumleitung auf die neuere Version der Assembly in der app.config-Ausgabedatei hinzu. Diese Umleitung überschreibt die Assemblyvereinheitlichung, die sonst erfolgen würde. Die app.config-Quelldatei wird nicht geändert. Beispiel: Ihre App verweist direkt auf eine Out-of-Band-.NET Framework-Komponente, verwendet jedoch eine Bibliothek von einem Drittanbieter, die sich auf eine frühere Version der gleichen Komponente bezieht. Wenn Sie die App kompilieren, wird die app.config-Ausgabedatei so geändert, dass sie eine Umleitung zu der neueren Version der Komponente enthält. Beim Erstellen einer Web-App erhalten Sie eine Buildwarnung bezüglich des Bindungskonflikts, was Ihnen wiederum die Möglichkeit gibt, der web.config-Quelldatei die erforderliche Bindungsumleitung hinzuzufügen.

Wenn Sie der Quell app.config Datei manuell Bindungs Umleitungen hinzufügen, versucht Visual Studio zum Zeitpunkt der Kompilierung, die Assemblys auf der Grundlage der von Ihnen hinzugefügten Bindungs Umleitungen zu vereinheitlichen. Wenn Sie zum Beispiel die folgende Bindungsumleitung für eine Assembly einfügen:

`<bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0" />`

Wenn ein anderes Projekt in Ihrer App auf die Version 1.0.0.0 der gleichen Assembly verweist, fügt die automatische Bindungsumleitung den folgende Eintrag zur app.config-Ausgabedatei hinzu, damit die App auf die Version 2.0.0.0 dieser Assemblys vereinheitlicht wird:

`<bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />`

Sie können die automatische Bindungs Umleitung aktivieren, wenn Ihre APP auf ältere Versionen der .NET Framework abzielt. Sie können dieses Standardverhalten überschreiben, indem Sie in der app.config-Datei für jede Assembly Informationen zur Bindungs Umleitung angeben oder indem Sie die Funktion für die Bindungs Umleitung ausschalten. Informationen dazu, wie Sie diese Funktion aktivieren oder deaktivieren, finden Sie unter Gewusst [wie: Aktivieren und Deaktivieren der automatischen Bindungs Umleitung](how-to-enable-and-disable-automatic-binding-redirection.md).

<a name="bypass_PP"></a>
### <a name="bypassing-publisher-policy"></a>Umgehen der Herausgeberrichtlinie
 Falls erforderlich, können Sie Herausgeberrichtlinien in der App-Konfigurationsdatei überschreiben. So können zum Beispiel neue Versionen von Assemblys, die als abwärts kompatibel gelten, eine Anwendung trotzdem lahmlegen. Wenn Sie die Herausgeber Richtlinie umgehen möchten, fügen Sie [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) dem- [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) Element in der APP-Konfigurationsdatei ein-Element hinzu, und legen Sie das **Apply** -Attribut auf **No**fest, das alle vorherigen **Yes** -Einstellungen überschreibt.

 `<publisherPolicy apply="no" />`

 Durch das Umgehen der Herausgeberrichtlinie bleibt Ihre App zwar lauffähig, doch sollten Sie dieses Problem auf jeden Fall dem Anbieter der Assembly mitteilen. Wenn eine Assembly über eine Herausgeberrichtliniendatei verfügt, sollte der Anbieter sicherstellen, dass seine Assembly abwärts kompatibel ist und Clients die neue Version in vollem Umfang nutzen können.

<a name="BKMK_Redirectingassemblyversionsatthemachinelevel"></a>
## <a name="redirecting-assembly-versions-at-the-machine-level"></a>Umleiten von Assemblyversionen auf Computerebene
 In seltenen Fällen kann es vorkommen, dass der Administrator möchte, dass sämtliche Apps auf einem Computer eine bestimmte Version einer Assembly verwenden. Das kann zum Beispiel der Fall sein, wenn alle Apps eine bestimmte Version nutzen sollen, weil bei dieser eine Sicherheitslücke geschlossen wurde. Wenn eine Assembly in der Konfigurationsdatei des Computers umgeleitet wird, werden alle auf diesem Computer installierten Apps, die bisher die alte Version verwendet haben, zu der neuen Version umgeleitet. Die Konfigurationsdatei des Computers überschreibt die per App-Konfigurationsdatei und Herausgeberrichtliniendatei getroffenen Festlegungen. Diese Datei befindet sich im Verzeichnis "%*runtime install path*%\Config". Das .NET Framework ist meist im Verzeichnis "%drive%\Windows\Microsoft.NET\Framework" installiert.

<a name="BKMK_Specifyingassemblybindinginconfigurationfiles"></a>
## <a name="specifying-assembly-binding-in-configuration-files"></a>Angeben der Assemblybindung in Konfigurationsdateien
 Beim Festlegen von Bindungsumleitungen verwenden Sie in sämtlichen Dateien – in der App-Konfigurationsdatei, der Computer-Konfigurationsdatei oder der Herausgeberrichtliniendatei - das gleiche XML-Format. Verwenden Sie das-Element, um eine Assemblyversion zu einer anderen umzuleiten [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) . Mit dem **oldVersion** -Attribut kann sowohl eine einzelne Assemblyversion als auch ein Bereich von Versionen angegeben werden. Mit dem `newVersion` -Attribut sollte nur eine einzige Version angegeben werden.  Beispielsweise wird durch `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` angegeben, dass die Common Language Runtime die Version 2.0.0.0 statt der Assemblyversionen zwischen 1.1.0.0 und 1.2.0.0 verwenden soll.

 Im folgenden Codebeispiel werden die unterschiedlichsten Szenarien von Bindungsumleitungen gezeigt. In diesem Beispiel wird für `myAssembly`eine Umleitung für einen Bereich von Versionen und für `mySecondAssembly`eine einzelne Bindungsumleitung angegeben. Außerdem wird festgelegt, dass die Herausgeberrichtliniendatei nicht die Bindungsumleitungen für `myThirdAssembly`überschreiben soll.

 Zum Binden einer Assembly müssen Sie die Zeichenfolge "urn: Schemas-Microsoft-com: ASM. v1" mit dem **xmlns** -Attribut im- [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) Tag angeben.

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

### <a name="limiting-assembly--bindings-to-a-specific-version"></a>Einschränken von Assemblybindungen auf eine bestimmte Version
 Mithilfe des **appliesTo** -Attributs für das- [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) Element in einer APP-Konfigurationsdatei können Sie Assemblybindungsverweise zu einer bestimmten Version des .NET Framework umleiten. Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird. Wenn kein **appliesTo** -Attribut angegeben ist, [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) gilt das-Element für alle Versionen der .NET Framework.

 Um zum Beispiel die Assemblybindung einer .NET Framework 3.5-Assembly umzuleiten, müssten Sie den folgenden XML-Code in die App-Konfigurationsdatei einfügen:

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

 Die Informationen für Umleitungen sind in Reihenfolge der Versionen einzugeben. So geben Sie beispielsweise erst die Informationen zum Umleiten der Assemblybindung für .NET Framework 3.5-Assemblys und dann die für .NET Framework 4.5-Assemblys ein. Geben Sie zuletzt die Informationen zum Umleiten der Assemblybindung für alle .NET Framework-Assemblyumleitungen ein, bei denen nicht das **appliesTo** -Attribut verwendet wird und die daher für alle Versionen .NET Framework-Versionen gelten. Falls bei der Umleitung Konflikte auftreten, wird die erste passende Umleitungsanweisung in der Konfigurationsdatei verwendet.

 Beispiel: Zum Umleiten eines Verweises auf eine .NET Framework 3.5-Assembly und eines anderen Verweises auf eine .NET Framework 4-Assembly müssten Sie nach dem folgenden Muster vorgehen:

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

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Aktivieren und Deaktivieren der Bindungsumleitung](how-to-enable-and-disable-automatic-binding-redirection.md)
- [\<bindingRedirect>-Element](./file-schema/runtime/bindingredirect-element.md)
- [Sicherheitsberechtigung für die Umleitung der Assemblybindung](assembly-binding-redirection-security-permission.md)
- [Assemblys in .NET](../../standard/assembly/index.md)
- [Programmieren mit Assemblys](../../standard/assembly/index.md)
- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps](index.md)
- [Schema für Laufzeiteinstellungen](./file-schema/runtime/index.md)
- [Konfigurationsdateischema](./file-schema/index.md)
- [Vorgehensweise: Erstellen einer Herausgeberrichtlinie](how-to-create-a-publisher-policy.md)
