---
title: Tlbexp.exe (Type Library Exporter-Tool)
description: Verwenden Sie „Tlbexp.exe“, das Tool zum Exportieren von Typbibliotheken. Dieses Tool generiert eine Typbibliothek, die die in einer Common Language Runtime-Assembly (CLR) definierten Typen beschreibt.
ms.date: 03/30/2017
helpviewer_keywords:
- exporting type library [.NET Framework]
- exporter tool [.NET Framework]
- Tlbexp.exe
- Type Library Exporter
- type libraries [.NET Framework], exporting
ms.assetid: a487d61b-d166-467b-a7ca-d8b52fbff42d
ms.openlocfilehash: e675b0addc9051a0b3c877e9b029e113c17ba5f0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543386"
---
# <a name="tlbexpexe-type-library-exporter"></a>Tlbexp.exe (Type Library Exporter-Tool)
Das Type Library Exporter-Tool generiert eine Typbibliothek, die die in einer Assembly der Common Language Runtime definierten Typen beschreibt.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
tlbexp assemblyName [options]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|*assemblyName*|Die Assembly, für die eine Typbibliothek exportiert werden soll.|  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/asmpath:** *directory*|Gibt den Speicherort an, der nach Assemblys durchsucht werden soll. Wenn Sie diese Option verwenden, müssen Sie die Speicherorte, die nach Assemblys durchsucht werden sollen, auf die verwiesen wird, explizit angeben, einschließlich des aktuellen Verzeichnisses.<br /><br /> Wenn Sie die **asmpath**-Option verwenden, sucht das Type Library Exporter-Tool nicht nach einer Assembly im globalen Assemblycache (GAC).|  
|**/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/names:** *filename*|Legt die Großschreibung von Namen in einer Typbibliothek fest. Das *filename*-Argument entspricht einer Textdatei. Jede Zeile in der Datei legt die Großschreibung eines in der Typbibliothek enthaltenen Namens fest.|  
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/oldnames**|Erzwingt, dass "Tlbexp.exe" ergänzte Typnamen exportiert, wenn ein Typnamenkonflikt vorliegt. Beachten Sie, dass dies das Standardverhalten in den Vorgängerversionen von .NET Framework Version 2.0 war.|  
|**/out:** *file*|Gibt den Namen der zu generierenden Typbibliotheksdatei an. Wenn Sie diese Option nicht angeben, generiert "Tlbexp.exe" eine Typbibliothek mit dem Namen der Assembly (der tatsächliche Assemblyname, der nicht mit dem Namen der Datei übereinstimmen muss, in der die Assembly enthalten ist) und einer Erweiterung ".tlb".|  
|**/silence:** `warningnumber`|Unterdrückt die Anzeige der angegebenen Warnung. Diese Option kann nicht zusammen mit **/silent** verwendet werden.|  
|**/silent**|Unterdrückt die Anzeige von Erfolgsmeldungen. Diese Option kann nicht zusammen mit **/silence** verwendet werden.|  
|**/tlbreference:** *typelibraryname*|Erzwingt, dass "Tlbexp.exe" Typbibliotheksverweise explizit auflöst, ohne auf die Registrierung zurückzugreifen. Wenn beispielsweise Assembly B auf Assembly A verweist, können Sie diese Option verwenden, um einen expliziten Typbibliotheksverweis anzugeben, statt auf die in der Registrierung angegebene Typbibliothek zurückzugreifen. "Tlbexp.exe" führt eine Versionsüberprüfung durch, um sicherzustellen, dass die Typbibliotheksversion mit der Assemblyversion übereinstimmt. Andernfalls wird ein Fehler generiert.<br /><br /> Beachten Sie, dass die **tlbreference**-Option dennoch auf die Registrierung zurückgreift, wenn das <xref:System.Runtime.InteropServices.ComImportAttribute>-Attribut auf eine Schnittstelle angewendet wird, die anschließend von einem anderen Typ implementiert wird.|  
|**/tlbrefpath:** *path*|Vollqualifizierter Pfad zu einer Typbibliothek, auf die verwiesen wird.|  
|**/win32**|Wenn auf einem 64-Bit-Computer kompiliert wird, gibt diese Option an, dass "Tlbexp.exe" eine 32-Bit-Typbibliothek generiert.|  
|**/win64**|Wenn auf einem 32-Bit-Computer kompiliert wird, gibt diese Option an, dass „tlbexp.exe“ eine 64-Bit-Typbibliothek generiert.|  
|**/verbose**|Gibt den ausführlichen Modus an. Es wird eine Liste aller Assemblys angezeigt, auf die verwiesen wird und für die eine Typbibliothek generiert werden muss.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
> [!NOTE]
> Bei den Befehlszeilenoptionen für "Tlbexp.exe" wird die Groß- und Kleinschreibung nicht beachtet, und die Optionen können in beliebiger Reihenfolge angegeben werden. Geben Sie die Option einfach so weit an, dass eine eindeutige Identifizierung möglich ist. Beispiel: **/n** entspricht **/nologo** und **/o:** *outfile.tlb* entspricht **/out:** *outfile.tlb*.  
  
## <a name="remarks"></a>Hinweise  
 "Tlbexp.exe" generiert eine Typbibliothek, die Definitionen der in der Assembly definierten Typen enthält. Anwendungen wie Visual Basic 6.0 können mithilfe der generierten Typbibliothek Bindungen zu den in der Assembly definierten .NET-Typen erstellen.  
  
> [!IMPORTANT]
> Sie können "Tlbexp.exe" nicht verwenden, um Windows-Metadatendateien (.winmd) zu exportieren. Das Exportieren von Windows Runtime-Assemblys wird nicht unterstützt.  
  
 Die Assembly wird immer vollständig konvertiert. Sie können mit Tlbexp.exekeine Typinformationen für einen Teil der in der Assembly definierten Typen generieren.  
  
 „Tlbexp.exe“ kann nicht zum Erstellen einer Typbibliothek aus einer Assembly verwendet werden, die mit dem [Type Library Importer-Tool (Tlbimp.exe)](tlbimp-exe-type-library-importer.md) importiert wurde. Stattdessen sollten Sie auf die ursprüngliche Typbibliothek verweisen, die mit "Tlbimp.exe" importiert wurde. Sie können eine Typbibliothek aus einer Assembly exportieren, die auf Assemblys verweist, die mit "Tlbimp.exe" importiert wurden. Weitere Informationen finden Sie im Abschnitt mit den Beispielen weiter unten.  
  
 "Tlbexp.exe" speichert generierte Typbibliotheken im aktuellen Arbeitsverzeichnis oder dem für die Ausgabedatei angegebenen Verzeichnis. Für eine einzelne Assembly können mehrere Typbibliotheken generiert werden.  
  
 "Tlbexp.exe" generiert eine Typbibliothek, registriert diese jedoch nicht. Dies steht im Gegensatz zum [Assembly Registration-Tool (Regasm.exe)](regasm-exe-assembly-registration-tool.md), das eine Typbibliothek generiert und gleichzeitig registriert. Verwenden Sie zum Generieren einer Typbibliothek und Registrieren in COM "Regasm.exe".  
  
 Wenn Sie weder die `/win32`- noch die `/win64`-Option angeben, generiert "Tlbexp.exe" eine 32-Bit- oder 64-Bit-Typbibliothek, die dem Computertyp entspricht, auf dem Sie die Kompilierung ausführen (32-Bit- oder 64-Bit-Computer). Bei Kreuzkompilierungen können Sie die `/win64`-Option auf einem 32-Bit-Computer zum Generieren einer 64-Bit-Typbibliothek verwenden, und Sie können die `/win32`-Option auf einem 64-Bit-Computer zum Generieren einer 32-Bit-Typbibliothek verwenden. In 32-Bit-Typbibliotheken ist der <xref:System.Runtime.InteropServices.ComTypes.SYSKIND>-Wert auf <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN32> festgelegt. In 64-Bit-Typbibliotheken ist der <xref:System.Runtime.InteropServices.ComTypes.SYSKIND>-Wert auf <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN64> festgelegt. Alle Datentyptransformationen (z. B. Datentypen in Zeigergröße wie `IntPtr` und `UIntPtr`) werden entsprechend konvertiert.  
  
 Wenn Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut verwenden, um einen <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType>-Wert `VT_UNKOWN` oder `VT_DISPATCH` anzugeben, ignoriert "Tlbexp.exe" jede nachfolgende Verwendung des Felds <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType>. Betrachten Sie die folgenden Signaturen:  
  
```csharp
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_UNKNOWN, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructUnkSafe(){return null;}  
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_DISPATCH, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructDispSafe(){return null;}  
```  
  
 Die folgende Typbibliothek wird generiert:  
  
```cpp
[id(0x60020004)]  
HRESULT StructUnkSafe([out, retval] SAFEARRAY(IUnknown*)* pRetVal);  
[id(0x60020005)]  
HRESULT StructDispSafe([out, retval] SAFEARRAY(IDispatch*)* pRetVal);  
```  
  
 Beachten Sie, dass "Tlbexp.exe" das Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> ignoriert.  
  
 Da Typbibliotheken nicht alle in den Assemblys gefundenen Informationen aufnehmen können, verwirft "Tlbexp.exe" während des Exportvorgangs möglicherweise einige Daten. Eine Erläuterung des Transformationsprozesses sowie Informationen darüber, wie Sie die Quelle der Informationen identifizieren, die an eine Typbibliothek ausgegeben werden, finden Sie unter [Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100)).  
  
 Beachten Sie, dass das Type Library Exporter-Tool Methoden exportiert, die über <xref:System.TypedReference>-Parameter als `VARIANT` verfügen, obwohl das <xref:System.TypedReference>-Objekt in nicht verwaltetem Code keine Bedeutung hat. Wenn Sie Methoden exportieren, die über <xref:System.TypedReference>-Parameter verfügen, generiert das Type Library Exporter-Tool keine Warnung und keinen Fehler, und nicht verwalteter Code, der die resultierende Typbibliothek verwendet, wird nicht ordnungsgemäß ausgeführt.  
  
 Das Type Library Exporter-Tool wird unter Microsoft Windows 2000 und höher unterstützt.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl generiert eine Typbibliothek mit dem Namen der in `myTest.dll` gefundenen Assembly.  
  
```console  
tlbexp myTest.dll  
```  
  
 Der folgende Befehl generiert eine Typbibliothek mit dem Namen `clipper.tlb`.  
  
```console  
tlbexp myTest.dll /out:clipper.tlb  
```  
  
 Das folgende Beispiel veranschaulicht die Verwendung von "Tlbexp.exe" zum Exportieren einer Typbibliothek aus einer Assembly, die auf andere mit "Tlbimp.exe" importierte Assemblys verweist.  
  
 Importieren Sie zunächst mit "Tlbimp.exe" die Typbibliothek `myLib.tlb`, und speichern Sie sie als `myLib.dll`.  
  
```console  
tlbimp myLib.tlb /out:myLib.dll  
```  
  
 Der folgende Befehl verwendet den C#-Compiler zum Kompilieren von `Sample.dll,`, die auf die im vorhergehenden Beispiel erstellte `myLib.dll` verweist.  
  
```console  
CSC Sample.cs /reference:myLib.dll /out:Sample.dll  
```  
  
 Der folgende Befehl generiert eine Typbibliothek für `Sample.dll`, die auf `myLib.dll` verweist.  
  
```console  
tlbexp Sample.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.TypeLibExporterFlags>
- [Extras](index.md)
- [Regasm.exe (Assembly Registration-Tool)](regasm-exe-assembly-registration-tool.md)
- [Zusammenfassung: Konvertieren einer Assembly in eine Typbibliothek](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))
- [Tlbimp.exe (Type Library Importer-Tool)](tlbimp-exe-type-library-importer.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
