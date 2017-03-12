---
title: "/link (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/l compiler option [C#]"
  - "/link compiler option [C#]"
  - "-l compiler option [C#]"
  - "EmbedInteropTypes"
  - "l compiler option [C#]"
  - "embed interop types [COM Interop]"
  - "-link compiler option [C#]"
  - "link compiler option [C#]"
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /link (C# Compiler Options)
Bewirkt, dass der Compiler dem Projekt, das Sie gerade kompilieren, COM\-Typinformationen in den angegebenen Assemblys bereitstellt.  
  
## Syntax  
  
```  
/link:fileList  
// -or-  
/l:fileList  
```  
  
## Argumente  
 `fileList`  
 Erforderlich.  Durch Kommas getrennte Liste von Assemblydateinamen.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ein.  
  
## Hinweise  
 Die `/link`\-Option aktiviert das Bereitstellen einer Anwendung mit eingebetteten Typinformationen.  Die Anwendung kann dann in einer Laufzeitassembly Typen verwenden, die die eingebetteten Typinformationen implementieren, und benötigt keinen Verweis auf die Laufzeitassembly.  Wenn verschiedene Versionen der Laufzeitassembly veröffentlicht werden, können die unterschiedlichen Versionen von der Anwendung mit den eingebetteten Typinformationen verwendet werden, ohne dass eine Neukompilierung erforderlich ist.  Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Die Verwendung der `/link`\-Option ist insbesondere bei der Arbeit mit COM‑Interop nützlich.  Sie können COM\-Typen einbetten, sodass auf dem Zielcomputer keine primäre Interopassembly \(Primary Interop Assembly, PIA\) mehr für die Anwendung erforderlich ist.  Die `/link`\-Option weist den Compiler an, die COM\-Typinformationen aus der Interopassembly, auf die verwiesen wird, in den resultierenden kompilierten Code einzubetten.  Der COM\-Typ wird vom CLSID \(GUID\)\-Wert bezeichnet.  Daher kann die Anwendung auf einem Zielcomputer ausgeführt werden, auf dem dieselben COM\-Typen mit denselben CLSID\-Werten installiert sind.  Ein gutes Beispiel sind Anwendungen, die Microsoft Office automatisieren.  Da Anwendungen wie Office normalerweise in verschiedenen Versionen denselben CLSID\-Wert beibehalten, kann die Anwendung die COM\-Typen verwenden, auf die verwiesen wird, sofern.NET Framework 4 oder höher auf dem Zielcomputer installiert ist und die Anwendung Methoden, Eigenschaften oder Ereignisse verwendet, die in den COM\-Typen enthalten sind, auf die verwiesen wird.  
  
 Die `/link`\-Option bettet nur Schnittstellen, Strukturen und Delegaten ein.  Das Einbetten von COM\-Klassen wird nicht unterstützt.  
  
> [!NOTE]
>  Wenn Sie im Code eine Instanz eines eingebetteten COM\-Typs erstellen, müssen Sie die Instanz mit der entsprechenden Schnittstelle erstellen.  Der Versuch, mit CoClass eine Instanz eines eingebetteten COM\-Typs zu erstellen, führt zu einem Fehler.  
  
 Um die `/link`\-Option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] festzulegen, fügen Sie einen Assemblyverweis hinzu, und legen Sie die `Embed Interop Types`\-Eigenschaft auf **true** fest.  Der Standardwert für die `Embed Interop Types`\-Eigenschaft ist **false**.  
  
 Wenn Sie eine Verknüpfung mit einer COM\-Assembly \(Assembly A\) herstellen, die wiederum auf eine andere COM\-Assembly \(Assembly B\) verweist, müssen Sie auch eine Verknüpfung mit Assembly B herstellen, wenn eine der folgenden Voraussetzungen erfüllt ist:  
  
-   Ein für Assembly A verwendeter Typ erbt von einem Typ oder implementiert eine Schnittstelle von Assembly B.  
  
-   Ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode mit einem Rückgabe\- oder Parametertyp aus Assembly B wird aufgerufen.  
  
 Ebenso wie die [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)\-Compileroption verwendet die `/link`\-Compileroption die Antwortdatei Csc.rsp, die auf häufig verwendete [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblys verweist.  Verwenden Sie die [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)\-Compileroption, wenn der Compiler die Datei Csc.rsp nicht verwenden soll.  
  
 Die Kurzform von `/link` ist `/l`.  
  
## Generika und eingebettete Typen  
 In den folgenden Abschnitten werden die Einschränkungen für die Verwendung von generischen Typen in Anwendungen beschrieben, die Interop\-Typen einbetten.  
  
### Generische Schnittstellen  
 Generische Schnittstellen, die von einer Interopassembly eingebettet werden, können nicht verwendet werden.  Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-cs[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#1)]  
  
### Typen mit generischen Parametern  
 Typen mit einem generischen Parameter, dessen Typ von einer Interopassembly eingebettet wird, können nicht verwendet werden, wenn dieser Typ aus einer externen Assembly stammt.  Diese Einschränkung gilt nicht für Schnittstellen.  Betrachten Sie z. B. die <xref:Microsoft.Office.Interop.Excel.Range>\-Schnittstelle, die in der <xref:Microsoft.Office.Interop.Excel>\-Assembly definiert wird.  Wenn eine Bibliothek Interop\-Typen aus der <xref:Microsoft.Office.Interop.Excel>\-Assembly einbettet und eine Methode verfügbar macht, die einen generischen Typ mit einem Parameter zurückgibt, dessen Typ die <xref:Microsoft.Office.Interop.Excel.Range>\-Schnittstelle ist, muss diese Methode eine generische Schnittstelle zurückgeben, wie im folgenden Codebeispiel gezeigt.  
  
 [!code-cs[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#2)]  
[!code-cs[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#3)]  
[!code-cs[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#4)]  
  
 Im folgenden Beispiel kann der Clientcode die Methode aufrufen, die die generische <xref:System.Collections.IList>\-Schnittstelle zurückgibt, ohne dass ein Fehler auftritt.  
  
 [!code-cs[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#5)]  
  
## Beispiel  
 Im folgenden Code werden die Quelldatei `OfficeApp.cs` und Verweisassemblys aus `COMData1.dll` und `COMData2.dll` kompiliert, um `OfficeApp.exe` zu erstellen.  
  
```c#  
csc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)   
 [\/noconfig \(Ignore csc.rsp\)](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)