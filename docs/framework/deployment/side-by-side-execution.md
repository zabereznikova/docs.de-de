---
title: Parallele Ausführung in .NET Framework
description: Erkunden Sie die parallele Ausführung in .NET. Die parallele Ausführung ermöglicht die Ausführung mehrerer Versionen einer Anwendung oder Komponenten auf demselben Computer.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution
ms.assetid: 649f1342-766b-49e6-a90d-5b019a751e11
ms.openlocfilehash: 6cd6fb73b27957fdea85cd9a92bf2aa3bafda1ce
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619402"
---
# <a name="side-by-side-execution-in-the-net-framework"></a>Parallele Ausführung in .NET Framework

Die parallele Ausführung bezeichnet die Möglichkeit, mehrere Versionen einer Anwendung oder einer Komponente auf demselben Computer auszuführen. Das bedeutet, dass Sie gleichzeitig mehrere Versionen der Common Language Runtime sowie mehrere Versionen von Anwendungen und Komponenten, die eine Version der Common Language Runtime verwenden, gleichzeitig auf demselben Computer ausführen können.  
  
Die folgende Abbildung zeigt verschiedene Anwendungen, die auf demselben Computer zwei unterschiedliche Versionen der Common Language Runtime verwenden. Anwendungen A, B und C verwenden Common Language Runtime, Version 1.0, während Anwendung D die Version 1.1 verwendet.  
  
![Parallele Ausführung verschiedener Laufzeitversionen](./media/side-by-side-execution/side-by-side-runtime-execution.gif)  
  
.NET Framework besteht aus der Common Language Runtime und einer Reihe von Assemblys, die die API-Typen enthalten. Die Versionsnummern der Common Language Runtime und der .NET Framework-Assemblys sind voneinander unabhängig. So ist z. B. die Common Language Runtime Version 4.0 eigentlich Version 4.0.319, während die Version 1.0 der .NET Framework-Assemblys eigentlich Version 1.0.3300.0 ist.  
  
Die folgende Abbildung zeigt verschiedene Anwendungen, die auf demselben Computer zwei unterschiedliche Versionen einer Komponente verwenden. Anwendungen A und B verwenden Version 1.0 der Komponente, während Anwendung C Version 2.0 der gleichen Komponente verwendet.  
  
![Diagramm der parallelen Ausführung einer Komponente](./media/side-by-side-execution/side-by-side-component-execution.gif)  
  
Durch die parallele Ausführung können Sie besser steuern, an welche Version einer Komponente eine Anwendung gebunden wird und welche Version der Common Language Runtime eine Anwendung verwendet.  
  
## <a name="benefits-of-side-by-side-execution"></a>Vorteile der parallelen Ausführung  

Vor der Entwicklung von Windows XP und .NET Framework traten DLL-Konflikte auf, da Anwendungen nicht zwischen inkompatiblen Versionen des gleichen Codes unterscheiden konnten. In einer DLL enthaltene Typinformationen waren lediglich an einen Dateinamen gebunden. Einer Anwendung war nicht bekannt, ob die in einer DLL enthaltenen Typen dieselben Typen waren, mit denen die Anwendung erstellt wurde. Dadurch konnten neue Versionen einer Komponente ältere Versionen überschreiben und ein ordnungsgemäßes Funktionieren von Anwendungen verhindern.  
  
Die parallele Ausführung und .NET Framework bieten die folgenden Features zur Vermeidung von DLL-Konflikten:  
  
- Assemblys mit starkem Namen  
  
     Die parallele Ausführung verwendet Assemblys mit starken Namen, um Typinformationen an eine bestimmte Version einer Assembly zu binden. Dadurch wird verhindert, dass eine Anwendung oder Komponente an eine ungültige Version einer Assembly gebunden wird. Assemblys mit starken Namen ermöglichen außerdem das Vorhandensein mehrerer Versionen einer Datei auf demselben Computer und deren Verwendung durch Anwendungen. Weitere Informationen finden Sie unter [Assemblys mit starkem Namen](../../standard/assembly/strong-named.md).  
  
- Versionsabhängige Codespeicherung  
  
     .NET Framework bietet versionsabhängige Codespeicherung im globalen Assemblycache. Der globale Asssemblycache ist ein Codecache für den gesamten Computer, der auf allen Computern vorhanden ist, auf denen .NET Framework installiert ist. Im Cache werden Assemblys anhand der Version, Kultur und Herstellerinformationen gespeichert, und es werden mehrere Versionen von Komponenten und Anwendungen unterstützt. Weitere Informationen finden Sie unter [Globaler Assemblycache](../app-domains/gac.md).  
  
- Isolation.  
  
     Mit .NET Framework können Sie Anwendungen und Komponenten erstellen, die isoliert ausgeführt werden. Isolation ist eine wesentliche Komponente der parallelen Ausführung. Sie umfasst sowohl die Erkennung der verwendeten Ressourcen als auch die zuverlässige gemeinsame Verwendung von Ressourcen durch mehrere Versionen einer Anwendung oder Komponente. Die Isolation umfasst außerdem das versionsspezifische Speichern von Dateien. Weitere Informationen zur Isolation finden Sie unter [Richtlinien für die Erstellung von Anwendungen und Komponenten für die parallele Ausführung](guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="version-compatibility"></a>Versionskompatibilität  

Die Versionen 1.0 und 1.1 von .NET Framework sind miteinander kompatibel. Eine mit .NET Framework, Version 1.0, erstellte Anwendung ist in Version 1.1 ausführbar, und eine mit .NET Framework, Version 1.1, erstellte Anwendung kann auch in Version 1.0 ausgeführt werden. Beachten Sie jedoch, dass die in Version 1.1 von .NET Framework neuen API-Funktionen nicht mit Version 1.0 von .NET Framework funktionieren. In Version 2.0 erstellte Anwendungen können nur mit Version 2.0 ausgeführt werden. Anwendungen für Version 2.0 können nicht mit Version 1.1 oder einer früheren Version ausgeführt werden.  
  
Versionen von .NET Framework werden als eine abgeschlossene Einheit behandelt, die aus Common Language Runtime und den zugeordneten .NET Framework-Assemblys bestehen. Dieses Konzept wird als Assemblyvereinheitlichung bezeichnet. Assemblybindungen können umgeleitet werden, um andere Versionen von .NET Framework-Assemblys einzubeziehen, das Überschreiben der Standardassemblybindung kann jedoch riskant sein und muss vor der Bereitstellung gründlich getestet werden.  
  
## <a name="locating-runtime-version-information"></a>Feststellen der Laufzeitversionsinformationen  

Informationen darüber, mit welcher Laufzeitversion eine Anwendung oder Komponente kompiliert wurde und welche der Laufzeitversionen für die Anwendung ausgeführt werden müssen, werden an zwei Orten gespeichert. Bei der Kompilierung einer Anwendung oder Komponente werden die Informationen über die für die Kompilierung verwendete Laufzeitversion in der verwalteten ausführbaren Datei gespeichert. Informationen über die für die Anwendung oder Komponente erforderlichen Laufzeitversionen werden in der Anwendungskonfigurationsdatei gespeichert.  
  
### <a name="runtime-version-information-in-the-managed-executable"></a>Laufzeitversionsinformationen in der verwalteten ausführbaren Datei  

Der Dateiheader der PE-Datei (Portable Executable, übertragbare ausführbare Datei) jeder verwalteten Anwendung und Komponente enthält Informationen über die Laufzeitversion, mit der diese erstellt wurde. Die Common Language Runtime verwendet diese Information, um die wahrscheinlichste Laufzeitversion zu bestimmen, die die Anwendung für die Ausführung benötigt.  
  
### <a name="runtime-version-information-in-the-application-configuration-file"></a>Laufzeitversionsinformationen in der Anwendungskonfigurationsdatei  

Zusätzlich zu den Informationen im Dateiheader der PE-Datei kann eine Anwendung auch über eine Anwendungskonfigurationsdatei verfügen, die die Informationen über die Laufzeitversion bereitstellt. Die Anwendungskonfigurationsdatei ist eine XML-Datei, die vom Anwendungsentwickler erstellt wird und mit der Anwendung ausgeliefert wird. Das [\<requiredRuntime>-Element](../configure-apps/file-schema/startup/requiredruntime-element.md) des [\<startup>-Abschnitts](../configure-apps/file-schema/startup/startup-element.md), wenn in dieser Datei vorhanden, gibt an, welche Versionen der Runtime und welche Versionen einer Komponente von der Anwendung unterstützt werden. Diese Datei kann auch beim Testen der Kompatibilität einer Anwendung mit verschiedenen Laufzeitversionen verwendet werden.  
  
Nicht verwalteter Code, einschließlich COM- und COM+-Anwendungen, können über Anwendungskonfigurationsdateien verfügen, die die Common Language Runtime für das Zusammenwirken mit verwaltetetem Code verwendet. Die Anwendungskonfigurationsdatei wirkt sich auf beliebigen verwalteten Code aus, der über COM aktiviert wird. Die Datei kann angeben, welche Laufzeitversionen unterstützt und welche Assemblyumleitungen durchgeführt werden. COM-Interop-Anwendungen, die verwalteten Code aufrufen, verwenden standardmäßig die zuletzt auf dem Computer installierte Laufzeitversion.  
  
 Weitere Informationen zu den Anwendungskonfigurationsdateien finden Sie unter [Konfigurationsdateien](../configure-apps/index.md).  
  
## <a name="determining-which-version-of-the-runtime-to-load"></a>Bestimmen der zu ladenden Laufzeitversion  

Die Common Language Runtime verwendet die folgenden Informationen, um zu bestimmen, welche Version der Runtime für eine Anwendung geladen werden soll:  
  
- Die verfügbaren Runtime-Versionen  
  
- Die Runtime-Versionen, die von einer Anwendung unterstützt werden  
  
### <a name="supported-runtime-versions"></a>Unterstützte Runtime-Versionen  

Die Common Language Runtime verwendet die Anwendungskonfigurationsdatei und den PE-Dateiheader (Portable Executable, übertragbare ausführbare Datei), um zu bestimmen, welche Version der Runtime von einer Anwendung unterstützt wird. Wenn keine Anwendungskonfigurationsdatei vorhanden ist, lädt die Runtime die im PE-Dateiheader der Anwendung angegebene Runtime-Version, sofern diese verfügbar ist.  
  
Wenn eine Anwendungskonfigurationsdatei vorhanden ist, bestimmt die Runtime die entsprechende zu ladende Runtime-Version anhand der Ergebnisse der folgenden Vorgehensweise:  
  
1. Die Runtime überprüft das [\<supportedRuntime>-Element](../configure-apps/file-schema/startup/supportedruntime-element.md) in der Konfigurationsdatei der Anwendung. Sind eine oder mehrere der unterstützten Runtime-Versionen vorhanden, die im **\<supportedRuntime>** -Element angegeben sind, lädt die Common Language Runtime die Runtime-Version, die im ersten **\<supportedRuntime>** -Element angegeben ist. Wenn diese Version nicht verfügbar ist, überprüft die Common Language Runtime das nächste **\<supportedRuntime>** -Element und versucht, die angegebene Runtime-Version zu laden. Wenn auch diese Runtime-Version nicht verfügbar ist, werden die weiteren **\<supportedRuntime>** -Elemente überprüft. Wenn keine der unterstützten Runtime-Versionen verfügbar ist, kann die Common Language Runtime keine Runtime-Version laden, und sie zeigt eine Meldung an (siehe Schritt 3).  
  
2. Die Common Language Runtime liest den PE-Dateiheader der ausführbaren Datei der Anwendung. Ist die im PE-Dateiheader angegebene Runtime-Version verfügbar, lädt die Common Language Runtime diese Version. Ist die angegebene Runtime-Version nicht verfügbar, sucht die Runtime nach einer Runtime-Version, für die Microsoft festgestellt hat, dass sie mit der Common Language Runtime-Version im PE-Dateiheader kompatibel ist. Wird diese Version nicht gefunden, wird die Vorgehensweise mit Schritt 3 fortgesetzt.  
  
3. Die Runtime zeigt eine Meldung an, in der mitgeteilt wird, dass die von der Anwendung unterstützte Runtime-Version nicht verfügbar ist. Die Common Language Runtime wird nicht geladen.  
  
    > [!NOTE]
    > Sie können die Anzeige dieser Meldung unterdrücken, indem Sie unter dem Registrierungsschlüssel „HKLM\Software\Microsoft\\.NETFramework“ den Wert „NoGuiFromShim“ oder indem Sie die Umgebungsvariable „COMPLUS_NoGuiFromShim“ verwenden. Beispielsweise können Sie die Meldung für Anwendungen unterdrücken, bei denen typischerweise keine Interaktion mit dem Benutzer vorgesehen ist (z. B. bei unbeaufsichtigten Installationen oder Windows-Diensten). Wenn die Anzeige dieser Meldung unterdrückt wird, schreibt die Common Language Runtime eine Meldung in das Ereignisprotokoll.  Legen Sie den Registrierungswert "NoGuiFromShim" auf 1 fest, um diese Meldung für alle Anwendungen auf einem Computer zu unterdrücken. Sie können aber auch die Umgebungsvariable "COMPLUS_NoGuiFromShim" auf 1 festlegen, um die Meldung für Anwendungen zu unterdrücken, die in einem bestimmten Benutzerkontext ausgeführt werden.  
  
> [!NOTE]
> Nachdem eine Runtime-Version geladen wurde, kann über Umleitungen von Assemblybindungen angegeben werden, dass eine andere Version einer einzelnen .NET Framework-Assembly geladen werden soll. Diese Umleitungen von Bindungen betreffen nur die spezielle Assembly, die umgeleitet wird.  
  
## <a name="partially-qualified-assembly-names-and-side-by-side-execution"></a>Teilweise gekennzeichnete Assemblynamen und parallele Ausführung  

Teilweise gekennzeichnete Assemblyverweise können lediglich zum Binden von Assemblies in einem Anwendungsverzeichnis verwendet werden, da sie eine mögliche Problemquelle bei der parallelen Ausführung darstellen. Vermeiden Sie teilweise gekennzeichnete Assemblyverweise in Ihrem Code.  
  
Um teilweise gekennzeichnete Assemblyverweise in Code zu verringern, können Sie das [\<qualifyAssembly>](../configure-apps/file-schema/runtime/qualifyassembly-element.md)-Element in einer Anwendungskonfigurationsdatei verwenden, um im Code vorhandene teilweise gekennzeichnete Assemblyverweise vollständig zu kennzeichnen (qualifizieren). Verwenden Sie das **\<qualifyAssembly>** -Element, um nur die Felder anzugeben, die im partiellen Verweis nicht festgelegt wurden. Die im **fullName**-Attribut aufgeführte Assemblyidentität muss alle Informationen enthalten, die für die vollständige Kennzeichnung (Qualifizierung) des Assemblynamens erforderlich sind: Assemblyname, öffentlicher Schlüssel, Kultur und Version.  
  
 Im folgenden Beispiel wird der Eintrag in der Anwendungskonfigurationsdatei dargestellt, mit dem die Assembly `myAssembly` vollständig qualifiziert wird.  
  
```xml  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
<qualifyAssembly partialName="myAssembly"
fullName="myAssembly,  
      version=1.0.0.0,
publicKeyToken=...,
      culture=neutral"/>
</assemblyBinding>
```  
  
 Wenn eine Assemblyladeanweisung auf `myAssembly` verweist, bewirken diese Einstellungen in der Konfigurationsdatei, dass die Common Language Runtime den teilweise qualifizierten Verweis auf `myAssembly` automatisch in einen vollqualifizierten Verweis übersetzt. So wird Assembly.Load("myAssembly") beispielsweise zu Assembly.Load("myAssembly, version=1.0.0.0, publicKeyToken=..., culture=neutral").  
  
> [!NOTE]
> Sie können die **LoadWithPartialName**-Methode verwenden, um die Einschränkung der Common Language Runtime zu umgehen, die verhindert, dass Assemblys mit partiellen Verweisen aus dem globalen Assemblycache geladen werden. Diese Methode sollte nur in Remoteszenarien verwendet werden, da sie bei paralleler Ausführung schnell Probleme verursachen kann.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[How to: Aktivieren und Deaktivieren der Bindungsumleitung](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)|Beschreibt, wie eine Anwendung an eine bestimmte Version einer Assembly gebunden wird.|  
|[Konfigurieren der Umleitung der Assemblybindung](configuring-assembly-binding-redirection.md)|Erläutert, wie Assemblybindungsverweise zur einer bestimmten Version der .NET Framework-Assemblys umgeleitet werden.|  
|[Prozessinterne parallele Ausführung](in-process-side-by-side-execution.md)|Erläutert, wie mehrere CLR-Versionen mithilfe der prozessinternen parallelen Laufzeithostaktivierung in einem Prozess ausgeführt werden können.|  
|[Assemblys in .NET](../../standard/assembly/index.md)|Bietet eine konzeptionelle Übersicht über Assemblys.|  
|[Anwendungsdomänen](../app-domains/application-domains.md)|Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.|  
  
## <a name="reference"></a>Referenz  

[\<supportedRuntime>-Element](../configure-apps/file-schema/startup/supportedruntime-element.md)
