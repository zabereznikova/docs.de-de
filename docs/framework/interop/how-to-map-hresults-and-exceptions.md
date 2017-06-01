---
title: "How to: Map HRESULTs and Exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interoperation with unmanaged code, HRESULTs"
  - "exceptions, HRESULTs"
  - "interoperation with unmanaged code, exceptions"
  - "HRESULTs"
  - "COM interop, HRESULTs"
  - "COM interop, exceptions"
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Map HRESULTs and Exceptions
COM\-Methoden melden Fehler durch die Rückgabe von HRESULTs, .NET\-Methoden dagegen durch das Auslösen von Ausnahmen.  Common Language Runtime verwaltet den Übergang zwischen beiden.  Jede Ausnahmeklasse in .NET Framework wird einem HRESULT zugeordnet.  
  
 Durch benutzerdefinierte Ausnahmeklassen kann festgelegt werden, welches HRESULT angemessen ist.  Durch diese Ausnahmeklassen kann das HRESULT dynamisch geändert werden, das beim Generieren einer Ausnahme zurückgegeben werden soll, indem das **HResult**\-Feld auf das Ausnahmeobjekt eingestellt wird.  Zusätzliche Informationen über die Ausnahme werden dem Client über die Schnittstelle **IErrorInfo** bereitgestellt, die auf dem .NET\-Objekt im nicht verwalteten Prozess implementiert ist.  
  
 Wenn Sie eine Klasse erstellen, die **System.Exception** erweitert, müssen Sie das `HRESULT`\-Feld während der Konstruktion festlegen.  Ansonsten weist die Basisklasse den `HRESULT`\-Wert zu.  Sie können neue Ausnahmeklassen einem vorhandenen HRESULT zuordnen, indem Sie den Wert im Konstruktor der Ausnahme angeben.  
  
 Beachten Sie, dass `HRESULT` von der Laufzeit zeitweise ignoriert werden kann, wenn der Thread `IErrorInfo` enthält.  Dieses Verhalten kann auftreten, wenn `HRESULT` und `IErrorInfo` nicht denselben Fehler darstellen.   ``  
  
### So erstellen Sie eine neue Ausnahmeklasse und ordnen diese einem HRESULT zu  
  
1.  Verwenden Sie den folgenden Code, um eine neue Ausnahmeklasse mit dem Namen `NoAccessException` zu erstellen und diese dem HRESULT `E_ACCESSDENIED` zuzuordnen.  
  
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
  
 Es kann vorkommen, dass ein Programm \(in einer beliebigen Programmiersprache\) gleichzeitig verwalteten und nicht verwalteten Code verwendet.  So verwendet z. B. der benutzerdefinierte Marshaller im folgenden Codebeispiel die **Marshal.ThrowExceptionForHR\(int HResult\)**\-Methode, um eine Ausnahme mit einem spezifischen `HRESULT`\-Wert auszulösen.  Die Methode sucht nach dem HRESULT und generiert den entsprechenden Ausnahmetyp.  Im folgenden Codefragment wird z. B. **ArgumentException** generiert.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 In der folgenden Tabelle wird eine vollständige Zuordnung eines jeden HRESULT zur vergleichbaren Ausnahmeklasse in .NET Framework angegeben.  
  
|HRESULT|.NET\-Ausnahme|  
|-------------|--------------------|  
|**MSEE\_E\_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR\_E\_APPLICATION**|**ApplicationException**|  
|**COR\_E\_ARGUMENT oder E\_INVALIDARG**|**ArgumentException**|  
|**COR\_E\_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR\_E\_ARITHMETIC oder ERROR\_ARITHMETIC\_OVERFLOW**|**ArithmeticException**|  
|**COR\_E\_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR\_E\_BADIMAGEFORMAT oder ERROR\_BAD\_FORMAT**|**BadImageFormatException**|  
|**COR\_E\_COMEMULATE\_ERROR**|**COMEmulateException**|  
|**COR\_E\_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR\_E\_CORE**|**CoreException**|  
|**NTE\_FAIL**|**CryptographicException**|  
|**COR\_E\_DIRECTORYNOTFOUND oder ERROR\_PATH\_NOT\_FOUND**|**DirectoryNotFoundException**|  
|**COR\_E\_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR\_E\_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR\_E\_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR\_E\_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR\_E\_EXCEPTION**|**Ausnahme**|  
|**COR\_E\_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR\_E\_FIELDACCESS**|**FieldAccessException**|  
|**COR\_E\_FILENOTFOUND oder ERROR\_FILE\_NOT\_FOUND**|**FileNotFoundException**|  
|**COR\_E\_FORMAT**|**FormatException**|  
|**COR\_E\_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR\_E\_INVALIDCAST oder E\_NOINTERFACE**|**InvalidCastException**|  
|**COR\_E\_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR\_E\_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR\_E\_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR\_E\_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR\_E\_IO**|**IOException**|  
|**COR\_E\_MEMBERACCESS**|**AccessException**|  
|**COR\_E\_METHODACCESS**|**MethodAccessException**|  
|**COR\_E\_MISSINGFIELD**|**MissingFieldException**|  
|**COR\_E\_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR\_E\_MISSINGMEMBER**|**MissingMemberException**|  
|**COR\_E\_MISSINGMETHOD**|**MissingMethodException**|  
|**COR\_E\_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR\_E\_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E\_NOTIMPL**|**NotImplementedException**|  
|**COR\_E\_NOTSUPPORTED**|**NotSupportedException**|  
|**COR\_E\_NULLREFERENCE oder E\_POINTER**|**NullReferenceException**|  
|**COR\_E\_OUTOFMEMORY oder**<br /><br /> **E\_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR\_E\_OVERFLOW**|**OverflowException**|  
|**COR\_E\_PATHTOOLONG oder ERROR\_FILENAME\_EXCED\_RANGE**|**PathTooLongException**|  
|**COR\_E\_RANK**|**RankException**|  
|**COR\_E\_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR\_E\_REMOTING**|**RemotingException**|  
|**COR\_E\_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR\_E\_SECURITY**|**SecurityException**|  
|**COR\_E\_SERIALIZATION**|**SerializationException**|  
|**COR\_E\_STACKOVERFLOW oder ERROR\_STACK\_OVERFLOW**|**StackOverflowException**|  
|**COR\_E\_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR\_E\_SYSTEM**|**SystemException**|  
|**COR\_E\_TARGET**|**TargetException**|  
|**COR\_E\_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR\_E\_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR\_E\_THREADABORTED**|**ThreadAbortException**|  
|**COR\_E\_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR\_E\_THREADSTATE**|**ThreadStateException**|  
|**COR\_E\_THREADSTOP**|**ThreadStopException**|  
|**COR\_E\_TYPELOAD**|**TypeLoadException**|  
|**COR\_E\_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR\_E\_VERIFICATION**|**VerificationException**|  
|**COR\_E\_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR\_E\_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**Alle anderen HRESULTs**|**COMException**|  
  
 Um erweiterte Fehlerinformationen abzurufen, muss der verwaltete Client die Felder des generierten Ausnahmeobjekts untersuchen.  Damit das Ausnahmeobjekt nützliche Fehlerinformationen bereitstellen kann, muss die Schnittstelle **IErrorInfo** durch das COM\-Objekt implementiert werden.  Die von **IErrorInfo** bereitgestellte Information wird von der Laufzeit zur Initialisierung des Ausnahmeobjekts verwendet.  
  
 Wenn das COM\-Objekt **IErrorInfo** nicht unterstützt, wird durch Common Language Runtime ein Ausnahmeobjekt mit Standardwerten initialisiert.  In der folgenden Tabelle wird jedes Feld aufgeführt, das einem Ausnahmeobjekt zugeordnet ist, und die Standardinformationsquelle angegeben, wenn das COM\-Objekt **IErrorInfo** unterstützt.  
  
 Beachten Sie, dass `HRESULT` von der Laufzeit zeitweise ignoriert werden kann, wenn der Thread `IErrorInfo` enthält.  Dieses Verhalten kann auftreten, wenn `HRESULT` und `IErrorInfo` nicht denselben Fehler darstellen.   ``  
  
|Ausnahmefeld|Informationsquelle von COM|  
|------------------|--------------------------------|  
|**ErrorCode**|Vom Aufruf zurückgegebenes HRESULT.|  
|**HelpLink**|Wenn **IErrorInfo\-\>HelpContext** nicht 0 ist, wird die Zeichenfolge durch Verkettung von **IErrorInfo\-\>GetHelpFile** und "\#" und **IErrorInfo\-\>GetHelpContext** geformt.  Andernfalls wird die Zeichenfolge von **IErrorInfo\-\>GetHelpFile** zurückgegeben.|  
|**InnerException**|Immer ein NULL\-Verweis \(**Nothing** in Visual Basic\).|  
|**Nachricht**|Von **IErrorInfo\-\>GetDescription** zurückgegebene Zeichenfolge.|  
|**Quelle**|Von **IErrorInfo\-\>GetSource** zurückgegebene Zeichenfolge.|  
|**StackTrace**|Die Stapelüberwachung.|  
|**TargetSite**|Name der Methode, die das fehlgeschlagene HRESULT zurückgegeben hat.|  
  
 Ausnahmefelder wie **Message**, **Source** und **StackTrace** sind für **StackOverflowException** nicht verfügbar.  
  
## Siehe auch  
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Ausnahmen](../../../docs/standard/exceptions/index.md)