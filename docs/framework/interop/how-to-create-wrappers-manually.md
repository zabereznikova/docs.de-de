---
title: 'Vorgehensweise: Manuelles Erstellen von Wrappern'
description: Erfahren Sie, wie Sie Wrapper von COM-Typen manuell erstellen. Verwenden Sie eine vorhandene IDL-Datei oder Typbibliothek, oder erstellen Sie verwaltete Deklarationen, und exportieren Sie die Assembly in eine Typbibliothek.
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
ms.openlocfilehash: 0321e98e6237e54397db7e583546fd69803ab7e1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275956"
---
# <a name="how-to-create-wrappers-manually"></a>Vorgehensweise: Manuelles Erstellen von Wrappern

Wenn Sie COM-Typen manuell in verwaltetem Quellcode deklarieren möchten, sollten Sie mit einer vorhandenen IDL-Datei oder -Typbibliothek (IDL, Interface Definition Language – Sprache für die Schnittstellendefinition) beginnen. Wenn Sie nicht über eine IDL-Datei verfügen oder keine Typbibliotheksdatei generieren können, können Sie die COM-Typen simulieren, indem Sie verwaltete Deklarationen erstellen und die sich daraus ergebende Assembly in eine Typbibliothek exportieren.  
  
### <a name="to-simulate-com-types-from-managed-source"></a>So simulieren Sie COM-Typen aus verwaltetem Quellcode  
  
1. Deklarieren Sie die Typen in einer Sprache, die mit der Common Language Specification (CLS) kompatibel ist, und kompilieren Sie die Datei.  
  
2. Exportieren Sie die Assembly, die die Typen enthält, mit dem [Type Library Exporter-Tool (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).  
  
3. Verwenden Sie die exportierte COM-Typbibliothek als Grundlage zum Deklarieren der COM-orientierten verwalteten Typen.  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a>So erstellen Sie einen durch die Laufzeit aufrufbaren Wrapper (RCW, Runtime Callable Wrapper)  
  
1. Wenn Sie über eine IDL-Datei oder eine Typbibliotheksdatei verfügen, legen Sie fest, welche Klassen und Schnittstellen Sie im benutzerdefinierten RCW einschließen möchten. Sie können alle Typen ausschließen, die Sie nicht direkt oder indirekt in der Anwendung verwenden möchten.  
  
2. Erstellen Sie eine Quelldatei in einer CLS-kompatiblen Sprache, und deklarieren Sie die Typen. Unter [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) finden Sie eine vollständige Beschreibung des Importkonvertierungsprozesses. Wenn Sie also einen benutzerdefinierten RCW erstellen, führen Sie im Wesentlichen die durch das [Type Library Importer-Tool (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) bereitgestellte Typkonvertierungsaktivität manuell durch. Das Beispiel im nächsten Abschnitt zeigt Typen in einer IDL- oder Typbibliotheksdatei sowie die zugehörigen Typen im C#-Code.  
  
3. Wenn die Deklarationen vollständig sind, kompilieren Sie die Datei so, wie Sie es für verwalteten Quellcode gewohnt sind.  
  
4. Analog zu den mit Tlbimp.exe importierten Typen benötigen einige Typen zusätzliche Informationen, die Sie dem Code direkt hinzufügen können. Weitere Informationen finden Sie unter [Vorgehensweise: Bearbeiten von Interopassemblys](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Code sind ein Beispiel der `ISATest`-Schnittstelle und der `SATest`-Klasse in IDL sowie die entsprechenden Typen im C#-Quellcode dargestellt.  
  
 **IDL-Datei oder -Typbibliotheksdatei**  
  
```cpp
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 **Wrapper in verwaltetem Quellcode**  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anpassen von Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))
- [COM-Datentypen](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))
- [How to: Bearbeiten von Interopassemblys](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))
- [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Type Library Exporter-Tool)](../tools/tlbexp-exe-type-library-exporter.md)
