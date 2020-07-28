---
title: .NET Framework-Tools
description: Hier erfahren Sie, welche .NET-Tools Ihnen das Erstellen, Bereitstellen und Verwalten von Anwendungen und Komponenten für .NET erleichtern.
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
ms.openlocfilehash: 0a5cbcd4fa60b819d3ab07a4f221e77ca106c321
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166854"
---
# <a name="net-framework-tools"></a>.NET Framework-Tools

Die .NET Framework-Tools erleichtern Ihnen das Erstellen, Bereitstellen und Verwalten von Anwendungen und Komponenten für .NET Framework.

Die meisten der in diesem Abschnitt beschriebenen .NET Framework-Tools werden automatisch mit Visual Studio installiert. Sie können Visual Studio von der [Visual Studio-Downloadseite](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) herunterladen.

Mit Ausnahme des Assembly Cache Viewer (*Shfusion.dll*) können Sie alle Tools von der Befehlszeile aus starten. Auf *Shfusion.dll* muss über den Datei-Explorer zugegriffen werden.
  
Die Befehlszeilentools führen Sie am besten über die Developer-Eingabeaufforderung für Visual Studio aus. Mit diesen Hilfsprogrammen können Sie die Tools einfacher ausführen, ohne zum Installationsordner navigieren zu müssen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

> [!NOTE]
> Einige Tools können nur auf 32-Bit-Computern oder auf 64-Bit-Computern ausgeführt werden. Stellen Sie sicher, dass Sie die entsprechende Version des Tools für Ihren Computer ausführen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Al.exe (Assembly Linker-Tool)](al-exe-assembly-linker.md)  
Generiert eine Datei mit einem Assemblymanifest aus Modulen oder Ressourcendateien.

- [Aximp.exe (Windows Forms ActiveX Control Importer-Tool)](aximp-exe-windows-forms-activex-control-importer.md)  
Konvertiert Typdefinitionen in einer COM-Typbibliothek für ein ActiveX-Steuerelement in ein Windows Forms-Steuerelement.

- [Caspol.exe (Richtlinientool für die Codezugriffssicherheit)](caspol-exe-code-access-security-policy-tool.md)  
Das Sicherheitsrichtlinientool für den Codezugriff ermöglicht es Ihnen, Sicherheitsrichtlinien auf der Ebene von Computer-, Benutzer- sowie Unternehmensrichtlinien anzuzeigen und zu konfigurieren. In .NET Framework 4 und höheren Versionen wirkt sich dieses Tool nur dann auf Richtlinien für die Codezugriffssicherheit (Code Access Security CAS) aus, wenn das [\<legacyCasPolicy>-Element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) auf `true` festgelegt ist. Weitere Informationen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

- [Cert2spc.exe (Software Publisher Certificate Test-Tool)](cert2spc-exe-software-publisher-certificate-test-tool.md)  
Erstellt ein SPC (Software Publisher's Certificate, Softwareherausgeberzertifikat) aus einem oder mehreren X.509-Zertifikaten. Dieses Tool wird ausschließlich zu Testzwecken verwendet.

- [Certmgr.exe (Certificate Manager-Tool)](certmgr-exe-certificate-manager-tool.md)  
Verwaltet Zertifikate, CTLs (Certificate Trust Lists, Zertifikatsvertrauenslisten) und CRLs (Certificate Revocation Lists, Zertifikatssperrlisten).

- [Clrver.exe (CLR-Versionstool)](clrver-exe-clr-version-tool.md)  
Führt alle installierten Versionen der Common Language Runtime (CLR) auf dem Computer auf.

- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)  
Ermöglicht eine einfachere Verwendung der .NET Framework-Tools. Es handelt sich um eine Eingabeaufforderung, die automatisch bestimmte Umgebungsvariablen festlegt.

- [CorFlags.exe (Konvertierungstool CorFlags)](corflags-exe-corflags-conversion-tool.md)  
Ermöglicht das Konfigurieren des CorFlags-Abschnitts eines PE-Imageheaders.

- [Fuslogvw.exe (Assembly Binding Log Viewer-Tool)](fuslogvw-exe-assembly-binding-log-viewer.md)  
Zeigt Informationen zu Assemblybindungen an und hilft Ihnen herauszufinden, warum eine Assembly von .NET Framework zur Laufzeit nicht gefunden werden kann.

- [Gacutil.exe (Global Assembly Cache-Tool)](gacutil-exe-gac-tool.md)  
Ermöglicht das Anzeigen und Bearbeiten des Inhalts des globalen Assemblycaches sowie des Downloadcaches.

- [Ilasm.exe (IL-Assembler)](ilasm-exe-il-assembler.md)  
Generiert eine portierbare ausführbare Datei (Portable Executable, PE) aus Zwischensprache (Intermediate Language, IL). Sie können die resultierende ausführbare Datei starten, um zu überprüfen, ob die IL wie erwartet ausgeführt wird.

- [Ildasm.exe (IL-Disassembler)](ildasm-exe-il-disassembler.md)  
Erfasst eine portierbare ausführbare Datei (PE-Datei), die Intermediate Language (IL)-Code enthält, und erstellt eine Textdatei, die in das IL Assembler-Tool (Ilasm.exe) eingegeben werden kann.

- [Installutil.exe (Installer-Tool)](installutil-exe-installer-tool.md)  
Ermöglicht das Installieren und Deinstallieren von Serverressourcen durch Ausführen der Installerkomponenten in einer bestimmten Assembly. (Kann mit Klassen im <xref:System.Configuration.Install>-Namespace verwendet werden.)

- [Lc.exe (License Compiler-Tool)](lc-exe-license-compiler.md)  
Liest Textdateien mit Informationen über die Lizenzierung und erstellt eine *LICENSES-Datei*, die als Ressource in eine ausführbare Datei der Common Language Runtime eingebettet werden kann.

- [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](mage-exe-manifest-generation-and-editing-tool.md)  
Ermöglicht das Erstellen, Bearbeiten und Signieren von Anwendungs- und Bereitstellungsmanifesten. Als Befehlszeilentool kann *Mage.exe* von Batchskripten und anderen Windows-basierten Anwendungen ausgeführt werden, beispielsweise ASP.NET-Anwendungen.

- [MageUI.exe (Tool zum Generieren und Bearbeiten von Manifesten, grafischer Client)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
Unterstützt dieselbe Funktionalität wie das Befehlszeilentool Mage.exe, verwendet jedoch eine Windows-basierte Benutzeroberfläche. Unterstützt dieselbe Funktionalität wie das Befehlszeilentool *Mage.exe*, verwendet jedoch eine Windows-basierte Benutzeroberfläche.

- [MDbg.exe (.NET Framework-Befehlszeilendebugger)](mdbg-exe.md)  
Erleichtert Anbietern von Tools und Entwicklern von Anwendungen das Suchen und Beheben von Fehlern in Programmen, die für die Common Language Runtime von .NET Framework entwickelt wurden. Dieses Tool stellt mithilfe der Debug-API Debugdienste bereit.

- [Mgmtclassgen.exe (Management Strongly Typed Class Generator-Tool)](mgmtclassgen-exe.md)  
Ermöglicht das Generieren einer früh gebundenen verwalteten Klasse für eine angegebene WMI (Windows Management Instrumentation)-Klasse.

- [Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)](mpgo-exe-managed-profile-guided-optimization-tool.md)  
Ermöglicht es Ihnen, die Assemblys von systemeigenen Images mithilfe allgemeiner Endbenutzerszenarien zu optimieren. „Mpgo.exe“ ermöglicht die Generierung und den Verbrauch von Profildaten für native Image-Anwendungsassemblys (nicht die .NET Framework-Assemblys) mithilfe der vom Anwendungsentwickler ausgewählten Aus- und Weiterbildungsszenarien.

- [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md)  
Verbessert die Leistung verwalteter Anwendungen durch die Verwendung von systemeigenen Images (Dateien mit kompiliertem prozessorspezifischen Maschinencode). Die Laufzeit kann systemeigene Abbilder aus dem Cache nutzen und muss nicht den JIT (Just-In-Time)-Compiler verwenden, um die ursprüngliche Assembly zu kompilieren.

- [Peverify.exe (PEVerify-Tool)](peverify-exe-peverify-tool.md)  
Hilft Ihnen, zu überprüfen, ob der MSIL-Code (Microsoft Intermediate Language) und zugeordnete Metadaten die Anforderungen an die Typsicherheit erfüllen.

- [Regasm.exe (Assembly Registration-Tool)](regasm-exe-assembly-registration-tool.md)  
Liest die Metadaten in einer Assembly und fügt der Registrierung die notwendigen Einträge hinzu. Dadurch können COM-Clients als .NET Framework-Klassen angezeigt werden.

- [Regsvcs.exe (.NET Services Installation-Tool)](regsvcs-exe-net-services-installation-tool.md)  
Lädt und registriert eine Assembly, generiert und installiert eine Typbibliothek in eine angegebene COM+ 1.0-Anwendung und konfiguriert Dienste, die Sie einer Klasse programmgesteuert hinzugefügt haben.

- [Resgen.exe (Resource File Generator)](resgen-exe-resource-file-generator.md)  
Konvertiert Textdateien ( *.txt* oder *.restext*) und Dateien im XML-basierten Ressourcenformat ( *.resx*) in binäre Dateien der Common Language Runtime ( *.resources*), die in eine ausführbare Binärdatei der Laufzeit eingebettet oder in Satellitenassemblys kompiliert werden können.

- [SecAnnotate.exe (.NET Security Annotator-Tool)](secannotate-exe-net-security-annotator-tool.md)  
Identifiziert den `SecurityCritical`- und den `SecuritySafeCritical`-Abschnitt einer Assembly.

- [SignTool.exe (Signaturtool)](signtool-exe.md)  
Signiert Dateien digital, überprüft Signaturen in Dateien und fügt Dateien einen Timestamp hinzu.

- [Sn.exe (Strong Name-Tool)](sn-exe-strong-name-tool.md)  
Erleichtert das Erstellen von Assemblys mit starkem Namen. Dieses Tool stellt Optionen zum Verwalten von Schlüsseln, Erzeugen und Überprüfen von Signaturen bereit.

- [SOS.dll (SOS-Debugerweiterung)](sos-dll-sos-debugging-extension.md)  
Hilft Ihnen beim Debuggen von verwalteten Anwendungen im WinDbg.exe-Debugger und in Visual Studio, indem Informationen über die interne Common Language Runtime-Umgebung (CLR) bereitgestellt werden.

- [SqlMetal.exe (Tool zur Codegenerierung)](sqlmetal-exe-code-generation-tool.md)  
Generiert Code und Zuordnungen für die LINQ to SQL-Komponente von .NET Framework.

- [Storeadm.exe (Isolated Storage-Tool)](storeadm-exe-isolated-storage-tool.md)  
Verwaltet den isolierten Speicher und stellt Optionen zur Verfügung, um den Speicher eines Benutzers aufzulisten und zu löschen.

- [Tlbexp.exe (Type Library Exporter-Tool)](tlbexp-exe-type-library-exporter.md)  
Generiert eine Typbibliothek, die die Typen beschreibt, die in einer Common Language Runtime-Assembly definiert sind.

- [Tlbimp.exe (Type Library Importer-Tool)](tlbimp-exe-type-library-importer.md)  
Konvertiert die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer Common Language Runtime-Assembly.

- [Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)](winmdexp-exe-windows-runtime-metadata-export-tool.md)  
Exportiert eine .NET Framework-Assembly, die als *WINMDOBJ-Datei* kompiliert ist, in eine Komponente der Windows-Runtime. Diese wiederum wird als *WINMD-Datei* gepackt und enthält sowohl die Metadaten als auch die Implementierungsinformationen für die Windows-Runtime.

- [Winres.exe (Windows Forms Resource Editor-Tool)](winres-exe-windows-forms-resource-editor.md)  
Unterstützt das Lokalisieren von Ressourcen der Benutzeroberfläche (*RESX*- oder *RESOURCES*-Dateien), die von Windows Forms verwendet werden. Sie können die Zeichenfolgen übersetzen und anschließend die Steuerelemente in der Größe anpassen, verschieben oder ausblenden, um die lokalisierten Zeichenfolgen anzupassen.

## <a name="related-sections"></a>Verwandte Abschnitte

- [WPF-Tools](https://docs.microsoft.com/previous-versions/ms742404(v=vs.110))  
Enthält Tools, z.B. das IsXPS-Konformitätstool (isXPS.exe) und Leistungsprofilerstellungstools.

- [Windows Communication Foundation-Tools](../wcf/tools.md)  
Enthält Tools, die das Erstellen, Bereitstellen und Verwalten von WCF (Windows Communication Foundation)-Anwendungen erleichtern.
