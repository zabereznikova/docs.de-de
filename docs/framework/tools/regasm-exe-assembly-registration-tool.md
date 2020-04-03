---
title: Regasm.exe (Assembly Registration-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Assembly Registration tool
- assemblies [.NET Framework], registering
- Regasm.exe
- registering assemblies
ms.assetid: e190e342-36ef-4651-a0b4-0e8c2c0281cb
ms.openlocfilehash: 0a1658e57f4a236e4bdd29c3ca224275c25ea727
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345006"
---
# <a name="regasmexe-assembly-registration-tool"></a>Regasm.exe (Assembly Registration-Tool)

Die Metadaten in einer Assembly werden vom Assembly Registration-Tool gelesen, und die erforderlichen Einträge werden der Registrierung hinzugefügt. COM-Clients sind so in der Lage, .NET Framework-Klassen transparent zu erstellen. Sobald eine Klasse registriert ist, kann diese von jedem COM-Client wie eine COM-Klasse verwendet werden. Die Klasse wird beim Installieren der Assembly nur einmal registriert. COM kann keine Instanzen von Klassen in der Assembly erstellen, bevor diese nicht registriert wurden.

Verwenden Sie zum Ausführen des Tools die Developer-Eingabeaufforderung für Visual Studio. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Geben Sie an der Eingabeaufforderung Folgendes ein:

## <a name="syntax"></a>Syntax

```console
regasm assemblyFile [options]
```

## <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*assemblyFile*|Die in COM zu registrierende Assembly.|

|Option|Beschreibung|
|------------|-----------------|
|**/codebase**|Es wird ein Codebase-Eintrag in der Registrierung erstellt. Mit dem Codebase-Eintrag wird der Dateipfad für eine Assembly festgelegt, die nicht im globalen Assemblycache installiert ist. Die Option sollte nicht angegeben werden, wenn Sie die zu registrierende Assembly später im globalen Assemblycache installieren. Bei dem mit der **/codebase**-Option festgelegten *assemblyFile*-Argument muss es sich um eine [Assembly mit starkem Namen](../../standard/assembly/strong-named.md) handeln.|
|**/registered**|Mit dieser Option wird angegeben, dass dieses Tool nur auf bereits registrierte Typbibliotheken verweist.|
|**/asmpath:directory**|Mit dieser Option wird ein Verzeichnis angegeben, in dem Assemblyverweise enthalten sind. Muss mit der Option **/regfile** verwendet werden|
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|
|**/regfile** [ **:** *regFile*]|Mit dieser Option wird die angegebene REG-Datei mit den erforderlichen Registrierungseinträgen für die Assembly generiert. Bei Angabe dieser Option wird die Registrierung nicht geändert. Sie können diese Option nicht zusammen mit der Option **/u** oder der Option **/tlb** verwenden.|
|**/silent** oder **/s**|Unterdrückt die Anzeige von Erfolgsmeldungen.|
|**/tlb** [ **:** *typeLibFile*]|Mit dieser Option wird eine Typbibliothek aus der angegebenen Assembly generiert, die Definitionen der in der Assembly definierten verfügbaren Typen enthält.|
|**/unregister** oder **/u**|Diese Option hebt die Registrierung der in *assemblyFile* gefundenen erstellbaren Klassen auf. Wenn Sie diese Option nicht angeben, registriert "Regasm.exe" die erstellbaren Klassen in der Assembly.|
|**/verbose**|Mit dieser Option wird der ausführliche Modus angegeben. Es wird eine Liste aller Assemblys angezeigt, auf die verwiesen wird und für die eine Typbibliothek generiert werden muss, wenn zusätzlich die Option **/tlb** angegeben wurde.|
|**/?** oder **/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|

> [!NOTE]
> Bei den Befehlszeilenoptionen für "Regasm.exe" wird die Groß- und Kleinschreibung nicht beachtet. Geben Sie die Option einfach so weit an, dass eine eindeutige Identifizierung möglich ist. Beispiel: **/n** entspricht **/nologo** und **/t:** *outfile.tlb* entspricht **/tlb:** *outfile.tlb*.

## <a name="remarks"></a>Hinweise

Mit der Option **/regfile** können Sie eine REG-Datei mit den Registrierungseinträgen generieren, anstatt die Änderungen direkt in der Registrierung vorzunehmen. Sie können die Registrierung auf einem Computer aktualisieren, indem Sie die REG-Datei mit dem Registrierungs-Editor (Regedit.exe) importieren. Beachten Sie, dass die REG-Datei keine Aktualisierungen der Registrierung enthält, die durch benutzerdefinierte Registrierungsfunktionen vorgenommen werden können.  Beachten Sie außerdem, dass die Option **/regfile** nur Registrierungseinträge für verwaltete Klassen ausgibt.  Diese Option gibt keine Einträge für `TypeLibID`s oder `InterfaceID`s aus.

Bei Angabe der Option **/tlb** wird von „regasm.exe“ eine Typbibliothek generiert und registriert, mit der die in der Assembly gefundenen Typen beschrieben werden. Die generierten Typbibliotheken werden von "Regasm.exe" im aktuellen Arbeitsverzeichnis oder in dem für die Ausgabedatei angegebenen Verzeichnis platziert. Beim Generieren einer Typbibliothek für eine Assembly, in der auf andere Assemblys verwiesen wird, werden ggf. mehrere Typbibliotheken gleichzeitig generiert. Sie können die Typbibliothek zum Bereitstellen von Typinformationen für Entwicklungstools wie Visual Studio verwenden. Die Option **/tlb** sollte nicht verwendet werden, wenn die zu registrierende Assembly mit dem Type Library Importer-Tool ([tlbimp.exe](tlbimp-exe-type-library-importer.md)) erstellt wurde. Sie können keine Typbibliothek aus einer Assembly exportieren, die von einer Typbibliothek importiert wurde. Das Verwenden der Option **/tlb** entspricht der Verwendung des Type Library Exporter-Tools ([tlbexp.exe](tlbexp-exe-type-library-exporter.md)) und von „regasm.exe“, wobei „tlbexp.exe“ die erstellte Typbibliothek allerdings nicht registriert.  Wenn Sie die Option **/tlb** zum Registrieren einer Typbibliothek verwenden, können Sie die Optionen **/tlb** zusammen mit der Option **/unregister** nutzen, um die Registrierung der Typbibliothek aufzuheben. Durch die gemeinsame Verwendung der beiden Optionen wird die Registrierung der Typbibliothek und der Schnittstelleneinträge aufgehoben, wodurch die Registrierung in beachtlichem Umfang bereinigt werden kann.

Wenn Sie eine Assembly für die Verwendung mit COM registrieren, werden der Registrierung des lokalen Computers von "Regasm.exe" Einträge hinzugefügt. Genauer gesagt werden versionsabhängige Registrierungsschlüssel erstellt, mit denen die parallele Ausführung mehrerer Versionen derselben Assembly auf einem Computer ermöglicht wird. Bei der erstmaligen Registrierung einer Assembly werden ein Schlüssel auf oberster Ebene für die Assembly und ein eindeutiger Unterschlüssel für die spezielle Version erstellt. Bei jeder Registrierung einer neuen Assemblyversion wird von "Regasm.exe" für die neue Version ein Unterschlüssel erstellt.

Als Beispiel dient ein Szenario, in dem Sie die verwaltete Komponente "myComp.dll, Version 1.0.0.0" für die Verwendung mit COM registrieren. Anschließend wird "myComp.dll, Version 2.0.0.0" registriert. Sie bestimmen, dass alle COM-Clientanwendungen auf dem verwendeten Computer "myComp.dll, Version 2.0.0.0" verwenden. Außerdem heben Sie die Registrierung von "myComp.dll, Version 1.0.0.0" auf. Dieses Registrierungsschema ermöglicht Ihnen die Aufhebung der Registrierung von „myComp.dll, Version 1.0.0.0“, da nur der Unterschlüssel für Version 1.0.0.0 entfernt wird.

Nach dem Registrieren einer Assembly mit „regasm.exe“ können Sie diese im [globalen Assemblycache](../app-domains/gac.md) installieren, sodass diese von jedem COM-Client aktiviert werden kann. Wenn die Assembly nur von einer einzelnen Anwendung aktiviert wird, können Sie diese im Verzeichnis der Anwendung platzieren.

## <a name="examples"></a>Beispiele

Mit dem folgenden Befehl werden alle in `myTest.dll` enthaltenen öffentlichen Klassen registriert.

```console
regasm myTest.dll
```

Mit dem folgenden Befehl wird die Datei `myTest.reg` generiert, in der alle erforderlichen Registrierungseinträge enthalten sind. Bei diesem Befehl wird die Registrierung nicht aktualisiert.

```console
regasm myTest.dll /regfile:myTest.reg
```

Mit dem folgenden Befehl werden alle in `myTest.dll` enthaltenen öffentlichen Klassen registriert. Außerdem wird die Typbibliothek `myTest.tlb`, in der die Definitionen aller in `myTest.dll` definierten öffentlichen Typen enthalten sind, generiert und registriert.

```console
regasm myTest.dll /tlb:myTest.tlb
```

## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](tlbexp-exe-type-library-exporter.md)
- [Tlbimp.exe (Type Library Importer-Tool)](tlbimp-exe-type-library-importer.md)
- [Registrieren von Assemblys bei COM](../interop/registering-assemblies-with-com.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
