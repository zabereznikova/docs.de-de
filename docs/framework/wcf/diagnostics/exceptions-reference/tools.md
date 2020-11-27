---
title: Tools
ms.date: 03/30/2017
ms.assetid: 89c907f9-313f-408c-992a-631f1eadf1da
ms.openlocfilehash: 2f7ef8b7f871dada676eb05713d6f624427d5395
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285693"
---
# <a name="tools"></a>Tools

In diesem Thema werden alle Ausnahmen aufgelistet, die von Windows Communication Foundation (WCF)-Tools generiert werden.

## <a name="exception-list"></a>Ausnahmeliste

|Ressourcencode|Ressourcenzeichenfolge|
|-------------------|---------------------|
|ParametersTarget|\<enum>|
|ParametersToolConfig|\<configFile>|
|ErrInvalidPath|Der angegebene Pfad ist ungültig. Überprüfen Sie das angegebene Argument.|
|ParametersReference|\<file path>|
|WrnCannotLoadConfigFileForValidation|Ein Fehler ist während der Verarbeitung der vom angegebenen Speicherort geladenen Konfigurationsdatei aufgetreten. Dienste, die in dieser Konfigurationsdatei definiert werden, können nicht überprüft werden.|
|MoreHelp|Geben Sie für weitere Hilfe „svcutil“ mit den angegebenen Argumenten ein.|
|HelpMergeConfig|Bewirkt, dass die generierte Konfiguration mit einer vorhandenen Datei zusammengeführt wird, statt die vorhandene Datei zu überschreiben.|
|ErrCannotWriteFile|Schreiben in eine Ausgabedatei nicht möglich.|
|ErrInvalidNamespaceArgument|Der angegebene ungültige Wert wurde an die angegebene Option übergeben. Geben Sie ein durch Trennzeichen getrenntes Paar aus Zielnamespace und CLR-Namespace an.|
|HelpImportXmlType|Konfiguriert das DataContract-Serialisierungsprogramm, um Nicht-DataContract-Typen als IXmlSerializable-Typen zu importieren.|
|ErrExclusiveOptionsSpecified|Die angegebene Option kann nicht verwendet werden, wenn die andere angegebene Option angegeben wurde.|
|WrnHttpGetFailed|HTTP GET-Fehler mit dem angegebenen URI.|
|ErrInputFileNotAssemblyOrMetadata|Die Datei an dem angegebenen Speicherort, die über das angegebene Eingabeargument gelesen wird, scheint keine XML-Metadatendatei oder keine gültige Assembly zu sein.|
|WrnUnknownMetadataFound|Nicht erkanntes Metadatendokument des angegebenen Typs kann nicht gespeichert werden.|
|ErrDirectoryContainsInvalidCharacters|Der angegebene ungültige Wert wurde an die angegebene Option übergeben. Das angegebene Zeichen ist in einem Pfad nicht zulässig.|
|WrnCannotResolveServiceForValidation|Es kann kein Dienst mit dem angegebenen configName geladen werden. Um einen Dienst zu überprüfen, stellen Sie sowohl die Assembly, die den Diensttyp enthält, als auch eine ausführbare Datei mit der Konfiguration für diesen Dienst bereit.|
|ErrUnexpectedValue|Es werden keine Werte von der angegebenen Option unterstützt.|
|#InvalidArg|Die Angabe enthält ein ungültiges Argument.|
|ParametersExcludeType|\<type>|
|HelpXmlSerializer|Generieren Sie Datentypen, die den XmlSerializer für die Serialisierung und die Deserialisierung verwenden.|
|#|---------------------------------------------------------------------------------------------------------------------=|
|ErrUnexpectedError|In dem Tool ist ein Fehler aufgetreten.|
|HelpNologo|Die Copyright- und Bannernachricht wird unterdrückt.|
|ErrInputConflictsWithTarget|Der Typ der Eingabe, der aus dem angegebenen Ziel gelesen wird, wird nicht unterstützt, wenn die angegebene Option auf den angegebenen Wert festgelegt ist.|
|WrnCannotLoadServiceForExport|Ein Fehler ist aufgetreten, während der zu exportierende Diensttyp geladen wurde.|
|HelpMetadataDownloadCategory|- = METADATEN-DOWNLOAD = -|
|WrnNoServiceContractTypes|Es können keine XmlSerializer-Typen für die angegebene Assembly generiert werden. Es wurden keine Dienstvertragstypen gefunden.|
|WrnCouldNotLoadTypesFromReferenceAssemblyAt|Während des Ladens von Typen in eine Assembly, die von der angegebenen Referenzassembly geladen wurde, ist ein Fehler aufgetreten. Einige Typen in der Assembly können nicht geladen werden und stehen für das Tool nicht zur Verfügung.|
|ErrDirectoryPointsToAFile|Der angegebene ungültige Wert wurde an die angegebene Option übergeben. Der angegebene Wert ist ein Pfad zu einer Datei.|
|Fehler|Error:|
|ErrDuplicateReferenceValues|Die angegebene Assembly wurde zweimal mit der angegebenen Option geladen. Es kann nur einmal auf eine Assembly verwiesen werden.|
|WrnNoXmlSerializerOperationBehavior|Es können keine XmlSerializer für die angegebene Assembly generiert werden. Kein Dienstvertrag in der Assembly verfügt über einen Vorgang mit XmlSerializerOperationBehavior.|
|ErrCannotCreateDirectory|Das angegebene Verzeichnis kann nicht erstellt werden.|
|ErrCouldNotLoadTypesFromAssemblyAt|Es können keine Typen in der angegebenen Assembly geladen werden.|
|ErrUnknownSwitch|Der angegebene Schalter ist eine nicht erkannte Option.|
|Logo|Das Logo des Tools ist "Microsoft ® Service Model Metadata Tool" mit Versionsangabe.|
|NoCodeWasGenerated|Es wurde kein Code generiert.<br /><br /> Wenn Sie versucht haben, einen Client zu generieren, könnte der Grund dafür sein, dass die Metadatendokumente keine gültigen Verträge oder Dienste enthielten<br /><br /> oder dass ermittelt wurde, dass alle Verträge/Dienste in Verweisassemblys vorhanden sind. Überprüfen Sie, dass Sie alle Metadatendokumente an das Tool weitergeleitet haben.|
|WrnUnableToLoadContractForSGen|Beim Laden eines Vertragstyps ist ein Fehler aufgetreten. Der XmlSerializer-Typ für diesen Vertrag kann nicht generiert werden. Der Typ und die Details werden angegeben.|
|WrnOptionConflictsWithInput|Die angegebene Option kann nicht mit mehreren Eingabeassemblys verwendet werden. Die angegebene Option wurde ignoriert.|
|ErrUnableToImportMetadata|Beim Versuch, Daten zu importieren, ist ein schwerwiegender Fehler aufgetreten.|
|ErrInvalidSerializer|Es wurde ein ungültiger Serialisierungsprogrammwert an die angegebene Option übergeben. Die unterstützten Serialisierungsprogramme werden angegeben.|
|SavingDownloadedMetadata|Speichern von heruntergeladenen Metadatendateien...|
|WrnNoConfigForServices|Keine der übergebenen Assemblys waren mit der Konfigurationsdatei ausführbar, oder keine der Konfigurationsdateien enthielt Dienste mit dem angegebenen Konfigurationsnamen.|
|ErrInputConflictsWithOption|Die aus der angegebenen Datei gelesene Eingabe kann nicht mit der angegebenen Option verwendet werden, da sie unterschiedliche Verwendungsarten des Tools voraussetzen.|
|ErrUnableToExportEndpoints|Beim Exports des angegebenen Diensttyps ist ein Fehler aufgetreten.|
|ErrInputSchemaParseError|Beim Lesen des angegebenen Eingabeschema ist ein XML-Schema-Analysefehler aufgetreten. Prüfen Sie, ob die XML wohlgeformt und gültig ist.|
|ErrInputPolicyParseError|Beim Lesen des angegebenen Eingabeschema ist ein WS-Richtlinien-Analysefehler aufgetreten. Prüfen Sie, ob die XML wohlgeformt und gültig ist.|
|ErrUnableToLoadReferenceType|Beim Laden eines referenzierten Vertragstyps ist ein Fehler aufgetreten. Dieser angegebene Typ wird ignoriert.|
|WrnCannotLoadServiceForValidation|Beim Laden des zu überprüfenden Diensts ist ein Fehler aufgetreten. Der Typ und die Details werden angegeben.|
|HelpCodeGenerationCategory|-= CODE-GENERIERUNG =-|
|RetreivingMetadataWithMexAndDisco|Es wird versucht, Metadaten vom angegebenen Speicherort mithilfe von WS-Metadata Exchange oder DISCO herunterzuladen.|
|ErrGeneralSchemaValidation|Bei der Überprüfung von XML-Schemas, die während des Exports generiert wurden, ist ein Fehler aufgetreten.|
|ParametersDirectory|\<directory>|
|ErrCannotLoadSpecifiedType|Es kann kein Typ für den angegebenen Wert geladen werden, der an die angegebene Option übergeben wurde. Stellen Sie sicher, dass die Assembly, zu der dieser Typ gehört, mit der angegebenen Option angegeben wird.|
|ErrOptionModeConflict|Die angegebene Option kann nicht mit der angegebenen Option verwendet werden, da sie unterschiedliche Ausgabetypen voraussetzen.|
|ErrIsNotAnAssembly|Die angegebene Datei kann nicht als Assembly geladen werden. Überprüfen Sie, ob diese Datei eine .NET-Assembly ist.|
|ErrInputConflictsWithMode|Die aus der angegebenen Datei gelesene Eingabe ist mit anderen Optionen nicht konsistent.|
|ErrDuplicateValuePassedToTypeArg|Der angegebene Wert wurde mehrmals an die angegebene Option übergeben. Jeder Typ kann nur einmal festgelegt werden.|
|ErrInputEPRFileParseError|Der Endpunktverweis kann nicht aus der angegebenen Datei gelesen werden. Prüfen Sie, ob die XML wohlgeformt und gültig ist.|
|ErrCouldNotCreateCodeProvider|Es kann kein Code Anbieter für den angegebenen Wert erstellt werden, der an das/-Argument übermittelt wurde {1} . Überprüfen Sie, dass der Codeanbieter ordnungsgemäß installiert und konfiguriert ist.|
|ErrPathTooLongDirOnly|Der resultierende angegebene Pfad ist zu lang. Überprüfen Sie das angegebene Argument.|
|HelpDataContractSerializer|Generieren Sie Datentypen, die das DataContract-Serialisierungsprogramm für die Serialisierung und die Deserialisierung verwenden.|
|ErrUnableToExportEndpoint|Beim Export des angegebenen Endpunktnamens im angegebenen Namespace im angegebenen Diensttyp, der in der für die Assembly geladenen Konfigurationsdatei gefunden wurde, ist ein Fehler aufgetreten.|
|HelpUsage1|Zeigt die Verwendung der Hilfe an.|
|HelpUsage2|Zeigt die Verwendung der Hilfe an.|
|HelpUsage3|Zeigt die Verwendung der Hilfe an.|
|HelpUsage4|Zeigt die Verwendung der Hilfe an.|
|HelpUsage5|Zeigt die Verwendung der Hilfe an.|
|ErrDirectoryNotFound|Das angegebene Verzeichnis kann nicht gefunden werden. Überprüfen Sie, dass das Verzeichnis vorhanden ist und dass Sie die entsprechenden Berechtigungen haben, es zu lesen.|
|ErrUnableToLoadFile|Die angegebene Datei kann nicht gelesen werden.|
|ErrNoFilesFound|Der angegebene Eingabepfad scheint nicht auf vorhandene Dateien zu verweisen.|
|ParametersConfig|\<configFile>|
|ErrDirectoryInsteadOfFile|Der angegebene Eingabepfad scheint ein Verzeichnis zu sein. Es müssen entweder URLs oder Dateipfade eingegeben werden.|
|HelpConfig|Weist die Tools an, eine Konfigurationsdatei mit dem bereitgestellten Namen zu generieren. Standard: output.config.|
|ErrSingleUseSwitch|Die angegebene Option kann nicht mehrmals angegeben werden.|
|Warnung|Warnung:|
|WrnAmbiguousServiceConfig|Es wurden mehrere Dienstkonfigurationen mit dem angegebenen Konfigurationsnamen gefunden. Die folgenden Assemblys werden angegeben.|
|ErrInvalidInputPath|Der angegebene Eingabepfad scheint nicht auf vorhandene Dateien zu verweisen und scheint kein gültiger URI zu sein.|
|ErrUnableToLoadInputs|Beim Lesen der geladenen Metadaten ist ein Fehler aufgetreten.|
|GeneratingSerializer|Generieren von XML-Serialisierungsprogrammen...|
|HelpToolConfig|Anstelle der Anwendungskonfigurationsdatei zu verwendende benutzerdefinierte Konfigurationsdatei. Diese kann verwendet werden, um die Metadatenkonfiguration zu ändern oder um Konfigurationserweiterungen zu registrieren, ohne die Konfigurationsdatei des Tools zu ändern.|
|ErrValidateInvalidUse|Die angegebene Option kann nicht zusammen mit der angegebenen Option verwendet werden.|
|WrnWSMExFailed|WS-Metadata Exchange-Fehler mit dem angegebenen URI.|
|HelpNoconfig|Generieren Sie keine Konfiguration.|
|HelpCodeGenerationDescription|Das angegebene Objekt kann Dienstverträge, Clients und Datentypen aus Metadatendokumenten generieren.|
|HelpTargetMetadata|Geben Sie Metadaten aus. Wenn die Eingabe eine URL ist, speichert Svcutil.exe die Metadaten auf dem Datenträger und generiert keinen Code. Wenn die Eingabe eine oder mehrere Assemblys sind, generiert Svcutil.exe Metadaten aus den Typen in den Assemblys.|
|ErrAmbiguousOptionModeConflict|Die angegebene Option verursacht Konflikte mit anderen Optionen. Überprüfen Sie die Verwendung des Tools.|
|ErrNotLanguageOrCodeDomType|Der angegebene Wert, der an das angegebene Argument übergeben wurde, stellt keine definierte Sprache dar und kann nicht als vollqualifizierter CLR-Typ geladen werden.|
|ErrUnableToUniquifyFilename|Es kann kein Ausgabedateiname erstellt werden. Es werden zu viele Dateien mit dem angegebenen Präfix erstellt.|
|ErrCannotCreateFile|Die angegebene Ausgabedatei kann nicht erstellt werden.|
|ErrExpectedValue|Die angegebene Option erfordert die Angabe eines Werts.|
|ErrCannotDisambiguateSpecifiedTypes|In dem Satz referenzierter Assemblys sind mehrere Typen mit identischem Namen vorhanden.  Verwenden Sie qualifizierte Assemblynamen, um zwischen den angegebenen Typen für die angegebene Option zu unterscheiden.|
|RetreivingMetadataWithMexOnly| Es wird versucht, Metadaten unter Verwendung von WS-Metadatenaustausch vom angegebenen Speicherort herunterzuladen. Diese URL unterstützt kein DISCO.|
|ErrInvalidTarget|Das angegebene Ziel ist ungültig, wenn es mit der angegebenen Option angegeben wird. Die unterstützten Ziele werden angegeben.|
|ErrPathTooLong|Der resultierende Pfad ist zu lang. Überprüfen Sie die angegebenen Argumente.|
|HelpCommonOptionsCategory|-= ALLGEMEINE OPTIONEN =-|
|ParametersServiceName|\<serviceConfigName>|
|ErrNoValidInputFilesSpecified|Es wurden keine gültigen Eingabedateien angegeben. Geben Sie entweder Metadatendokumente oder Assemblydateien an.|
|ParametersLanguage|\<language>|
|ErrUnableToLoadMetadataDocument|Beim Lesen der Metadaten aus einem der geladenen Dokumente ist ein Fehler aufgetreten. Der Dokumentbezeichner wird angegeben.|
|ErrConflictingInputs|Das angegebene Eingabeargument verursacht Konflikte mit der angegebenen Eingabe, da sie unterschiedliche Verwendungsarten des Tools voraussetzen.|
|WrnUnableToLoadContractForValidation|Beim Laden eines Vertragstyps ist ein Fehler aufgetreten. Der Typ und die Details werden angegeben.|
|WrnAttributeReflectionErrors|Die Attributreflektion ist für einige der Typen in der Assembly, die aus dem angegebenen Speicherort geladen wurden, fehlgeschlagen. Überprüfen Sie, dass diese Assembly von diesem Speicherort mit den richtigen Sicherheitsrechten geladen werden kann.|
|HelpMetadataExportCategory|- = METADATENEXPORT = -|
|HelpValidationCategory|- = DIENST-VALIDIERUNG = -|
|ValidationError|Validierungsfehler:|
|GeneratingFiles|Generieren von Dateien...|
|ErrCannotSpecifyMultipleMappingsForNamespace|Ein ungültiger Wert wurde an die angegebene Option übergeben. Der angegebene Zielnamespace kann nicht, wie angegeben, mehreren CLR-Namespaces zugeordnet werden.|
|ErrCouldNotLoadReferenceAssemblyAt|Die angegebene Referenzassembly kann nicht geladen werden.|
|ParametersOut|\<file>|
|NoCodeWasGeneratedSuggestDCOnly|Verwenden Sie zum Generieren von Verträgen aus den Schemas die angegebene Option.|
|ErrUnableToLoadInputConfig|Die angegebene Konfigurationsdatei kann nicht geladen werden.|
|ErrUnexpectedDelimiter|Ein ungültiges Argumenttrennzeichen (':' oder '=') kann die Option nicht starten.|
|ErrMergeConfigUsedWithoutConfig|Die angegebene Option kann nicht ohne Angabe der anderen angegebenen Optionen verwendet werden.|
|ErrUnableToExportContract|Beim Export des aus dem angegebenen Typ geladenen Vertrags ist ein Fehler aufgetreten.|
|GeneratingMetadata|Generieren von Metadatendateien...|
|ErrNotCodeDomType|Der angegebene Typ, der an das angegebene Argument übergeben wurde, gehört nicht zu der angegebenen abgeleiteten Klasse.|
|WrnNoTypeForServices|Keine der Assemblys, die übergeben wurden, enthielt Diensttypen mit dem angegebenen Konfigurationsnamen.|
|ErrAssemblyLoadFailed|Die angegebene Datei kann nicht als Assembly geladen werden. Überprüfen Sie die FusionLogs auf weitere Informationen.|
|NoMetadataWasGenerated|Es wurden keine Metadatendateien generiert. Es wurden keine Dienstverträge exportiert.<br /><br />  Verwenden Sie zum Exportieren eines Diensts die angegebene Option. Geben Sie zum Exportieren von Datenverträgen die Option an.|
|WrnCannotResolveServiceForExport|Es kann kein Dienst mit dem angegebenen configName geladen werden. Stellen Sie zum Exportieren eines Diensts die Assembly, die den Diensttyp enthält, und eine ausführbare Datei mit der Konfiguration für diesen Dienst bereit.|
|ParametersCollectionType|\<type>|
|ErrOptionConflictsWithTarget|Die Verwendung der angegebenen Option wird nicht unterstützt, wenn die angegebene Option auf den angegebenen Wert festgelegt ist.|
|ErrCodegenError|Beim Generieren von Code in der angegebenen Sprache ist ein Fehler aufgetreten.<br /><br /> Die Sprache unterstützt nicht alle Codeelemente, die generiert werden. Es sollte eine andere Sprache verwendet werden.|
|ErrInputWsdlParseError|Beim Lesen des angegebenen Eingabeschemas ist ein WSDL-Analysefehler aufgetreten. Prüfen Sie, ob die XML wohlgeformt und gültig ist.|
|ErrCouldNotCreateInstance|Es kann keine Instanz des angegebenen Typs erstellt werden, der an das angegebene Argument übergeben wurde.|
|ParametersNamespace|\<string,string>|
|HelpNostdlib|Verweisen Sie nicht auf Standardbibliotheken (standardmäßig wird auf mscorlib.dll und system.servicemodel.dll verwiesen.)|
|WrnCannotLoadConfigFileForExport|Bei der Verarbeitung der vom angegebenen Speicherort geladenen Konfigurationsdatei ist ein Fehler aufgetreten. Dienste, die in dieser Konfigurationsdatei definiert werden, können nicht geladen werden.|
|WrnUnableToLoadContractForExport|Beim Laden eines Vertragstyps ist ein Fehler aufgetreten. Dieser angegebene Typ kann nicht exportiert werden.|
