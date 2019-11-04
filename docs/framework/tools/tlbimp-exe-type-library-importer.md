---
title: Tlbimp.exe (Type Library Importer-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- type libraries [.NET Framework], importing
- importing type library
- Tlbimp.exe
- type definition conversion
- Type Library Importer
- type libraries
- converting type definitions
ms.assetid: ec0a8d63-11b3-4acd-b398-da1e37e97382
ms.openlocfilehash: fcbbc99c06e7c9666d58133bef20b84ef40c98d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104331"
---
# <a name="tlbimpexe-type-library-importer"></a>Tlbimp.exe (Type Library Importer-Tool)
Das Type Library Importer-Tool konvertiert die Typdefinitionen einer COM-Typbibliothek in äquivalente Definitionen einer Common Language Runtime-Assembly. Die Ausgabe von "Tlbimp.exe" besteht aus einer binären Datei (einer Assembly), die Laufzeitmetadaten für die in der ursprünglichen Typbibliothek definierten Typen enthält. Diese Datei können Sie mit Tools wie [Ildasm.exe](ildasm-exe-il-disassembler.md) überprüfen.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
tlbimp tlbFile [options]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|*tlbFile*|Der Name einer beliebigen Datei, die eine COM-Typbibliothek enthält.|  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/asmversion:** *versionnumber*|Gibt die Versionsnummer der zu erstellenden Assembly an. Geben Sie *versionnumber* im Format *major.minor.build.revision* an.|  
|**/company:** `companyinformation`|Fügt der Ausgabeassembly Unternehmensinformationen hinzu.|  
|**/copyright:** `copyrightinformation`|Fügt der Ausgabeassembly Copyrightinformationen hinzu. Diese Informationen können im Dialogfeld **Dateieigenschaften** für die Assembly angezeigt werden.|  
|**/delaysign**|Legt fest, dass "Tlbimp.exe" die resultierende Assembly mit einem starken Namen verzögert signiert. Sie müssen diese Option entweder zusammen mit der Option **/keycontainer:** , **/keyfile:** oder **/publickey:** angeben. Weitere Informationen zum verzögerten Signieren finden Sie unter [Verzögertes Signieren einer Assembly](../../standard/assembly/delay-sign.md).|  
|**/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/keycontainer:** *containername*|Signiert die resultierende Assembly mit einem starken Namen, wobei das Paar aus privatem und öffentlichem Schlüssel aus dem Schlüsselcontainer verwendet wird, der mit *containername* angegeben wurde.|  
|**/keyfile:** *filename*|Signiert die resultierende Assembly unter Verwendung des unter *filename* angegebenen Paar aus privatem und öffentlichem Schlüssel mit einem starken Namen.|  
|**/machine:** `machinetype`|Erstellt eine Assembly, die auf den angegebenen Computertyp (Mikroprozessor) ausgerichtet ist. Unterstützte Computertypen: x86, x64, Itanium und plattformübergreifende Typen.|  
|**/namespace:** *namespace*|Gibt den Namespace an, in dem die Assembly erstellt werden soll.|  
|**/noclassmembers**|Verhindert, dass "Tlbimp.exe" Member Klassen hinzufügt. Dadurch wird eine mögliche <xref:System.TypeLoadException> verhindert.|  
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/out:** *filename*|Gibt den Namen der Ausgabedatei, der Assembly und des Namespaces an, in dem die Metadatendefinitionen geschrieben werden sollen. Die **/out**-Option hat keine Auswirkung auf den Namespace der Assembly, wenn in der Typbibliothek die benutzerdefinierten Attribute der IDL (Interface Definition Language) angegeben sind. Diese steuern explizit den Namespace der Assembly. Wenn Sie diese Option nicht angeben, schreibt "Tlbimp.exe" die Metadaten in eine Datei, die den von der aktuellen Typbibliothek in der Eingabedatei definierten Namen trägt, und weist dieser die Erweiterung ".dll" zu. Stimmt der Name der Ausgabedatei mit dem der Eingabedatei überein, wird eine Fehlermeldung ausgegeben, um ein Überschreiben der Typbibliothek zu verhindern.|  
|**/primary**|Erstellt für die angegebene Typbibliothek eine primäre Interopassembly. Der Assembly wird der Hinweis hinzugefügt, dass der Herausgeber der Typbibliothek die Assembly erstellt hat. Sie unterscheiden die Assembly eines Verlegers von beliebigen anderen Assemblys, die mit "Tlbimp.exe" aus der Typbibliothek erstellt werden, indem Sie eine primäre Interopassembly angeben. Verwenden Sie nur die **/primary**-Option, wenn Sie der Verleger der Typbibliothek sind, die mit „Tlbimp.exe“ importiert wird. Beachten Sie, dass Sie eine primäre Interopassembly mit einem [starken Namen](../../standard/assembly/strong-named.md) signieren müssen. Weitere Informationen finden Sie unter [Primäre Interopassemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).|  
|**/product:** `productinformation`|Fügt der Ausgabeassembly Produktinformationen hinzu. Diese Informationen können im Dialogfeld **Dateieigenschaften** für die Assembly angezeigt werden.|  
|**/productversion:** `productversioninformation`|Fügt der Ausgabeassembly die Produktversion hinzu. Es gibt keine Formateinschränkungen. Diese Informationen können im Dialogfeld **Dateieigenschaften** für die Assembly angezeigt werden.|  
|**/publickey:** *filename*|Gibt die Datei an, die den öffentlichen Schlüssel zum Signieren der resultierenden Assembly enthält. Wenn Sie die Option **/keyfile:** oder **/keycontainer:** anstelle der Option **/publickey:** angeben, generiert „Tlbimp.exe“ den öffentlichen Schlüssel aus dem über **/keyfile:** bzw. **/keycontainer:** bereitgestellten Paar aus privatem und öffentlichem Schlüssel. Die Option **/publickey:** unterstützt Testschlüssel und Szenarien für verzögertes Signieren. Die Datei weist das von "Sn.exe" generierte Format auf. Weitere Informationen finden Sie unter der **-p**-Option von „Sn.exe“ unter [Strong Name-Tool (Sn.exe)](sn-exe-strong-name-tool.md).|  
|**/reference:** *filename*|Gibt die Assemblydatei an, die für das Auflösen von Verweisen auf Typen verwendet werden soll, die außerhalb der aktuellen Typbibliothek definiert sind. Wenn Sie die Option **/reference** nicht angeben, importiert „Tlbimp.exe“ automatisch rekursiv jede externe Typbibliothek, auf die die zu importierende Typbibliothek verweist. Wenn Sie die Option **/reference** angeben, versucht das Tool zunächst, die externen Typen in den verwiesenen Assemblys aufzulösen, bevor es andere Typbibliotheken importiert.|  
|**/silence:** `warningnumber`|Unterdrückt die Anzeige der angegebenen Warnung. Diese Option kann nicht zusammen mit **/silent** verwendet werden.|  
|**/silent**|Unterdrückt die Anzeige von Erfolgsmeldungen. Diese Option kann nicht zusammen mit **/silence** verwendet werden.|  
|**/strictref**|Eine Typbibliothek wird nicht importiert, wenn das Tool nicht alle Verweise in der aktuellen Assembly, in den mit der Option **/reference** angegebenen Assemblys oder in den registrierten primären Interopassemblys auflösen kann.|  
|**/strictref:nopia**|Entspricht **/strictref**, ignoriert jedoch primäre Interopassemblys.|  
|**/sysarray**|Gibt die Anweisung an das Tool, ein SafeArray im COM-Format als verwalteten <xref:System.Array>-Typ zu importieren|  
|**/tlbreference:** *filename*|Gibt die zum Auflösen der Verweise auf Typbibliotheken zu verwendende Typbibliotheksdatei an, ohne Einträge aus der Registrierung abzurufen.<br /><br /> Beachten Sie, dass bei dieser Option einige ältere Typbibliotheksformate nicht geladen werden.  Sie können jedoch ältere Typbibliotheksformate implizit über die Registrierung oder das aktuelle Verzeichnis laden.|  
|**/trademark:** `trademarkinformation`|Fügt der Ausgabeassembly Markeninformationen hinzu. Diese Informationen können im Dialogfeld **Dateieigenschaften** für die Assembly angezeigt werden.|  
|**/transform:** *transformname*|Konvertiert Metadaten entsprechend dem Parameter *transformname*.<br /><br /> Geben Sie **dispret** für den Parameter *transformname* an, um [out, retval]-Parameter der Methoden für auf Dispatch beschränkte Schnittstellen (Disp-Schnittstellen) in Rückgabewerte zu konvertieren.<br /><br /> Weitere Informationen über diese Option finden Sie in den Beispielen weiter unten in diesem Thema.|  
|**/unsafe**|Erstellt Schnittstellen ohne .NET Framework-Sicherheitsüberprüfungen. Eine auf diese Weise verfügbar gemachte Methode aufzurufen, kann ein Sicherheitsrisiko darstellen. Sie sollten diese Option nur verwenden, wenn Sie die Risiken abschätzen können, die das Verfügbarmachen von derartigem Code beinhaltet.|  
|**/verbose**|Gibt den ausführlichen Modus an und zeigt zusätzliche Informationen über die importierte Typbibliothek an.|  
|**/VariantBoolFieldToBool**|Konvertiert `VARIANT_BOOL`-Felder in Strukturen in <xref:System.Boolean>.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
> [!NOTE]
> Bei den Befehlszeilenoptionen für "Tlbimp.exe" wird die Groß- und Kleinschreibung nicht beachtet, und die Optionen können in beliebiger Reihenfolge angegeben werden. Geben Sie die Option einfach so weit an, dass eine eindeutige Identifizierung möglich ist. Damit entspricht **/n** z.B. **/nologo** ,und **/ou:** *outfile.dll* entspricht **/out:** *outfile.dll*.  
  
## <a name="remarks"></a>Anmerkungen  
 "Tlbimp.exe" führt Konvertierungen für eine ganze Typbibliothek auf einmal durch. Typinformationen zu einer Teilmenge der in einer einzelnen Typbibliothek definierten Typen können Sie mithilfe dieses Tools nicht generieren.  
  
 Es ist oft hilfreich oder notwendig, Assemblys [starke Namen](../../standard/assembly/strong-named.md) zuweisen zu können. Daher beinhaltet "Tlbimp.exe" Optionen, um die zur Generierung von Assemblys mit starken Namen notwendigen Informationen bereitzustellen. Sowohl die Option **/keyfile:** als auch die Option **/keycontainer:** signieren Assemblys mit starken Namen. Darum ist es sinnvoll, jeweils nur eine dieser Optionen zur Verfügung zu stellen.  
  
 Sie können mehrere Verweisassemblys angeben, indem Sie die Option **/reference** mehrmals verwenden.
 
 Aufgrund der Art, wie „Tlbimp.exe“ Assemblys generiert, ist es nicht möglich, eine Assembly einer anderen `mscorlib`-Version neu zuzuweisen. Wenn Sie beispielsweise eine Assembly generieren möchten, die .NET Framework 2.0 verwendet, müssen Sie die im .NET Framework 2.0/3.0/3.5 SDK enthaltene „Tlbimp.exe“-Datei verwenden. Bei Verwendung von .NET Framework 4.x müssen Sie die im .NET Framework 4.x SDK enthaltene „Tlbimp.exe“-Datei verwenden.
 
 Beim Importieren einer Typbibliothek aus einem Modul mit mehreren Typbibliotheken kann optional eine Ressourcen-ID an eine Typbibliothekdatei angehängt werden. "Tlbimp.exe" kann diese Datei nur finden, wenn sie sich im aktuellen Verzeichnis befindet oder der vollständige Pfad angegeben wird. Siehe das Beispiel weiter unten in diesem Thema.  
  
## <a name="examples"></a>Beispiele  
 Durch folgenden Befehl wird eine Assembly generiert, die den von der Typbibliothek in `myTest.tlb` gefundenen Namen und die Erweiterung ".dll" aufweist.  
  
```console  
tlbimp myTest.tlb   
```  
  
 Der folgende Befehl generiert eine Assembly mit dem Namen `myTest.dll`.  
  
```console  
tlbimp  myTest.tlb  /out:myTest.dll  
```  
  
 Durch folgenden Befehl wird eine Assembly generiert, die den Namen der Typbibliothek, die von `MyModule.dll\1` angegeben wurde, und die Erweiterung „.dll“ aufweist. `MyModule.dll\1` muss sich im aktuellen Verzeichnis befinden.  
  
```console  
tlbimp MyModule.dll\1  
```  
  
 Durch folgenden Befehl wird eine Assembly mit dem Namen `myTestLib.dll` für die Typbibliothek `TestLib.dll` generiert. Die Option **/transform:dispret** konvertiert beliebige [out, retval]-Parameter von Methoden für Disp-Schnittstellen in der Typbibliothek in Rückgabewerte in der verwalteten Bibliothek.  
  
```console  
tlbimp TestLib.dll /transform:dispret /out:myTestLib.dll  
```  
  
 Die Typbibliothek `TestLib.dll` im vorangegangenen Beispiel verfügt über eine dispinterface-Methode mit dem Namen `SomeMethod`, die "void" zurückgibt und einen [out, retval]-Parameter aufweist. Der folgende Code stellt die Signatur der Typbibliotheksmethode für `SomeMethod` in `TestLib.dll` dar.  
  
```cpp  
void SomeMethod([out, retval] VARIANT_BOOL*);  
```  
  
 Durch Angabe der Option **/transform:dispret** wird „Tlbimp.exe“ veranlasst, den `[out, retval]`-Parameter von `SomeMethod` in einen `bool`-Rückgabewert zu transformieren. Der folgende Code zeigt die Methodensignatur, die „Tlbimp.exe“ für `SomeMethod` in der verwalteten Bibliothek `myTestLib.dll` erstellt, wenn die Option **/transform:dispret** angegeben wird.  
  
```csharp  
bool SomeMethod();  
```  
  
 Wenn Sie „Tlbimp.exe“ verwenden, um eine verwaltete Bibliothek für `TestLib.dll` zu erstellen, ohne **/transform:dispret** anzugeben, erstellt das Tool die folgende Methodensignatur für `SomeMethod` in der verwalteten Bibliothek `myTestLib.dll`.  
  
```csharp  
void SomeMethod(out bool x);  
```  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](tlbexp-exe-type-library-exporter.md)
- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](../interop/importing-a-type-library-as-an-assembly.md)
- [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Ildasm.exe (IL-Disassembler)](ildasm-exe-il-disassembler.md)
- [Sn.exe (Strong Name-Tool)](sn-exe-strong-name-tool.md)
- [Assemblys mit starkem Namen](../../standard/assembly/strong-named.md)
- [Attribute zum Importieren von Typbibliotheken in Interop-Assemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y6a7ak23(v=vs.100))
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
