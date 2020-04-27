---
title: 'Vorgehensweise: Zuordnen von HRESULT-Werten und Ausnahmen'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- interoperation with unmanaged code, HRESULTs
- exceptions, HRESULTs
- interoperation with unmanaged code, exceptions
- HRESULTs
- COM interop, HRESULTs
- COM interop, exceptions
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
ms.openlocfilehash: e186228d1dc9a42ddfe92428f7dfad29a5789095
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181397"
---
# <a name="how-to-map-hresults-and-exceptions"></a>Vorgehensweise: Zuordnen von HRESULT-Werten und Ausnahmen
COM-Methoden melden Fehler durch die Rückgabe von HRESULTs; .NET Methoden melden sie durch das Auslösen von Ausnahmen. Die Common Language Runtime verwaltet den Übergang zwischen den beiden. Jede Ausnahmeklasse in .NET Framework wird einem HRESULT zugeordnet.  
  
 Benutzerdefinierte Ausnahmeklassen können jedes angemessene HRESULT angeben. Diese Ausnahmeklassen können durch eine dynamische Änderung einstellen, dass das HRESULT zurückgegeben wird, wenn die Ausnahme durch Festlegen des **HResult**-Felds für das Ausnahmeobjekt generiert wird. Weitere Informationen zur Ausnahme wird dem Client über die **IErrorInfo**-Schnittstelle zur Verfügung gestellt, die auf das .NET-Objekt im nicht verwalteten Prozess implementiert wird.  
  
 Wenn Sie eine Klasse erstellen, die **System.Exception** erweitert, müssen Sie während der Erstellung das HRESULT-Feld festlegen. Ansonsten weist die Basisklasse den HRESULT-Wert zu. Sie können neue Ausnahmeklassen einem vorhandenen HRESULT zuordnen, indem Sie den Wert im Konstruktor der Ausnahme bereitstellen.  
  
 Beachten Sie, dass die Common Language Runtime manchmal eine `HRESULT` ignoriert, wenn ein `IErrorInfo` im Thread vorhanden ist.  Dieses Verhalten kann in Fällen auftreten, in denen die `HRESULT` und `IErrorInfo` nicht den gleichen Fehler darstellen.  
  
### <a name="to-create-a-new-exception-class-and-map-it-to-an-hresult"></a>Erstellen einer neuen Ausnahmeklasse und Zuweisen zu einem HRESULT  
  
1. Verwenden Sie den folgenden Code zum Erstellen einer neuen Ausnahmeklasse namens `NoAccessException`, und ordnen Sie sie dem HRESULT `E_ACCESSDENIED` zu.  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 Es wird möglicherweise ein Programm (in einer beliebigen Programmiersprache) auftreten, das verwalteten und nicht verwalteten Code gleichzeitig verwendet. Beispielsweise verwendet der benutzerdefinierte Marshaller im folgenden Codebeispiel die Methode **Marshal.ThrowExceptionForHR(Int HResult)** , um eine Ausnahme mit einem bestimmten HRESULT-Wert auszulösen. Die Methode sucht das HRESULT und generiert den entsprechenden Ausnahmetyp. Im folgenden Codefragment generiert HRESULT z.B. **ArgumentException**.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 Die folgende Tabelle stellt die vollständige Zuordnung von jedem HRESULT zu seiner vergleichbaren Ausnahmeklasse in .NET Framework bereit.  
  
|HRESULT|.NET-Ausnahme|  
|-------------|--------------------|  
|**MSEE_E_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR_E_APPLICATION**|**ApplicationException**|  
|**COR_E_ARGUMENT oder E_INVALIDARG**|**ArgumentException**|  
|**COR_E_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR_E_ARITHMETIC oder ERROR_ARITHMETIC_OVERFLOW**|**ArithmeticException**|  
|**COR_E_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR_E_BADIMAGEFORMAT oder ERROR_BAD_FORMAT**|**BadImageFormatException**|  
|**COR_E_COMEMULATE_ERROR**|**COMEmulateException**|  
|**COR_E_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR_E_CORE**|**CoreException**|  
|**NTE_FAIL**|**CryptographicException**|  
|**COR_E_DIRECTORYNOTFOUND oder ERROR_PATH_NOT_FOUND**|**DirectoryNotFoundException**|  
|**COR_E_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR_E_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR_E_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR_E_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR_E_EXCEPTION**|**Exception**|  
|**COR_E_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR_E_FIELDACCESS**|**FieldAccessException**|  
|**COR_E_FILENOTFOUND oder ERROR_FILE_NOT_FOUND**|**FileNotFoundException**|  
|**COR_E_FORMAT**|**FormatException**|  
|**COR_E_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR_E_INVALIDCAST oder E_NOINTERFACE**|**InvalidCastException**|  
|**COR_E_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR_E_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR_E_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR_E_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR_E_IO**|**IOException**|  
|**COR_E_MEMBERACCESS**|**AccessException**|  
|**COR_E_METHODACCESS**|**MethodAccessException**|  
|**COR_E_MISSINGFIELD**|**MissingFieldException**|  
|**COR_E_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR_E_MISSINGMEMBER**|**MissingMemberException**|  
|**COR_E_MISSINGMETHOD**|**MissingMethodException**|  
|**COR_E_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR_E_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E_NOTIMPL**|**NotImplementedException**|  
|**COR_E_NOTSUPPORTED**|**NotSupportedException**|  
|**COR_E_NULLREFERENCE orE_POINTER**|**NullReferenceException**|  
|**COR_E_OUTOFMEMORY oder**<br /><br /> **E_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR_E_OVERFLOW**|**OverflowException**|  
|**COR_E_PATHTOOLONG oder ERROR_FILENAME_EXCED_RANGE**|**PathTooLongException**|  
|**COR_E_RANK**|**RankException**|  
|**COR_E_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR_E_REMOTING**|**RemotingException**|  
|**COR_E_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR_E_SECURITY**|**SecurityException**|  
|**COR_E_SERIALIZATION**|**SerializationException**|  
|**COR_E_STACKOVERFLOW oder ERROR_STACK_OVERFLOW**|**StackOverflowException**|  
|**COR_E_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR_E_SYSTEM**|**SystemException**|  
|**COR_E_TARGET**|**TargetException**|  
|**COR_E_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR_E_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR_E_THREADABORTED**|**ThreadAbortException**|  
|**COR_E_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR_E_THREADSTATE**|**ThreadStateException**|  
|**COR_E_THREADSTOP**|**ThreadStopException**|  
|**COR_E_TYPELOAD**|**TypeLoadException**|  
|**COR_E_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR_E_VERIFICATION**|**VerificationException**|  
|**COR_E_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR_E_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**Alle anderen HRESULTs**|**COMException**|  
  
 Um erweiterte Fehlerinformationen abzurufen, muss der verwaltete Client die Felder des erstellten Ausnahmeobjekts untersuchen. Das COM-Objekt muss die **IErrorInfo**-Schnittstelle implementieren, damit das Ausnahmeobjekt nützliche Informationen zu einem Fehler zur Verfügung stellen kann. Die Common Language Runtime verwendet die von **IErrorInfo** bereitgestellten Informationen zur Initialisierung des Ausnahmeobjekts.  
  
 Wenn das COM-Objekt **IErrorInfo** nicht unterstützt, initialisiert die Common Language Runtime ein Ausnahmeobjekt mit Standardwerten. In der folgenden Tabelle wird jedes Feld aufgeführt, das einem Ausnahmeobjekt zugewiesen ist, und die Quelle der Standardinformationen identifiziert, wenn das COM-Objekt **IErrorInfo** unterstützt.  
  
 Beachten Sie, dass die Common Language Runtime manchmal eine `HRESULT` ignoriert, wenn ein `IErrorInfo` im Thread vorhanden ist.  Dieses Verhalten kann in Fällen auftreten, in denen die `HRESULT` und `IErrorInfo` nicht den gleichen Fehler darstellen.  
  
|Ausnahmefeld|Informationsquelle von COM|  
|---------------------|------------------------------------|  
|**ErrorCode**|Vom Aufruf zurückgegebenes HRESULT.|  
|**HelpLink**|Wenn **IErrorInfo->HelpContext** ungleich 0 ist, wird die Zeichenfolge durch Verketten von **IErrorInfo->GetHelpFile** und „#“ sowie **IErrorInfo->GetHelpContext** gebildet. Andernfalls wird die Zeichenfolge aus **IErrorInfo->GetHelpFile** zurückgegeben.|  
|**InnerException**|Immer ein NULL-Verweis (**Nothing** in Visual Basic).|  
|**Meldung**|Von **IErrorInfo->GetDescription** zurückgegebene Zeichenfolge.|  
|**Quelle**|Von **IErrorInfo->GetSource** zurückgegebene Zeichenfolge.|  
|**StackTrace**|Die Stapelüberwachung.|  
|**TargetSite**|Der Name der Methode, die das fehlerhafte HRESULT zurückgegeben hat.|  
  
 Ausnahmefelder, wie z.B. **Message**, **Source** und **StackTrace** sind für die **StackOverflowException** nicht verfügbar.  
  
## <a name="see-also"></a>Siehe auch

- [Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Ausnahmen](../../standard/exceptions/index.md)
