---
title: Err Object
keywords: vblr6.chm1012954
f1_keywords:
- vblr6.chm1012954
ms.prod: office
api_name:
- Office.Err
ms.assetid: 23c9697a-9c6b-18f8-2b86-a0735f082c67
ms.date: 06/08/2017
---


# Err Object



<<<<<<< HEAD
Contains information about [run-time errors](../../Glossary/vbe-glossary.md).

## Remarks

The [properties](../../Glossary/vbe-glossary.md) of the **Err** object are set by the generator of an error — Visual Basic, an object, or the programmer.
=======
Contains information about [run-time errors](../../Glossary/vbe-glossary.md#run-time-error).

## Remarks

The [properties](../../Glossary/vbe-glossary.md#property) of the **Err** object are set by the generator of an error — Visual Basic, an object, or the programmer.
>>>>>>> master

The default property of the  **Err** object is **Number**. Because the default property can be represented by the object name **Err**, earlier code written using the **Err** function or **Err** statement doesn't have to be modified.

When a run-time error occurs, the properties of the  **Err** object are filled with information that uniquely identifies the error and information that can be used to handle it. To generate a run-time error in your code, use the **Raise** method.

The  **Err** object's properties are reset to zero or zero-length strings ("") after an **Exit Sub**, **Exit Function**, **Exit Property** or **Resume Next** statement within an error-handling routine. Using any form of the **Resume** statement outside of an error-handling routine will not reset the **Err** object's properties. The **Clear** method can be used to explicitly reset **Err**.

Use the  **Raise** method, rather than the **Error** statement, to generate run-time errors for system errors and class modules. Using the **Raise** method in other code depends on the richness of the information you want to return.

<<<<<<< HEAD
The  **Err** object is an intrinsic object with global [scope](../../Glossary/vbe-glossary.md). There is no need to create an instance of it in your code.
=======
The  **Err** object is an intrinsic object with global [scope](../../Glossary/vbe-glossary.md#scope). There is no need to create an instance of it in your code.
>>>>>>> master


## Example

This example uses the properties of the  **Err** object in constructing an error-message dialog box. Note that if you use the **Clear** method first, when you generate a Visual Basic error with the **Raise** method, Visual Basic's default values become the properties of the **Err** object.


```vb
Dim Msg
' If an error occurs, construct an error message
On Error Resume Next    ' Defer error handling.
Err.Clear
Err.Raise 6    ' Generate an "Overflow" error.
' Check for error, then show message.
If Err.Number <> 0 Then
<<<<<<< HEAD
    Msg = "Error # " &; Str(Err.Number) &; " was generated by " _
            &; Err.Source &; Chr(13) &; Err.Description
=======
    Msg = "Error # " & Str(Err.Number) & " was generated by " _
            & Err.Source & Chr(13) & Err.Description
>>>>>>> master
    MsgBox Msg, , "Error", Err.Helpfile, Err.HelpContext
End If

```

## See also

[Handle Run-Time Errors in VBA](../../../access/Concepts/Error-Codes/elements-of-run-time-error-handling.md)



[Raise Method](raise-method.md)
[Trappable Errors](trappable-errors.md)
