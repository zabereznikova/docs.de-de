---
title: ODBC-Schemaauflistungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="ca66b-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="ca66b-102">ODBC Schema Collections</span></span>
<span data-ttu-id="ca66b-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="ca66b-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="ca66b-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="ca66b-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="ca66b-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="ca66b-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ca66b-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="ca66b-106">Tables</span></span>  
  
-   <span data-ttu-id="ca66b-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="ca66b-107">Indexes</span></span>  
  
-   <span data-ttu-id="ca66b-108">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-108">Columns</span></span>  
  
-   <span data-ttu-id="ca66b-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-109">Procedures</span></span>  
  
-   <span data-ttu-id="ca66b-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ca66b-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ca66b-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ca66b-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="ca66b-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ca66b-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="ca66b-113">Tables and Views</span></span>  
  
|<span data-ttu-id="ca66b-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-114">ColumnName</span></span>|<span data-ttu-id="ca66b-115">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-116">TABLE_CAT</span></span>|<span data-ttu-id="ca66b-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-117">String</span></span>|  
|<span data-ttu-id="ca66b-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-118">TABLE_SCHEM</span></span>|<span data-ttu-id="ca66b-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-119">String</span></span>|  
|<span data-ttu-id="ca66b-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-120">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-121">String</span></span>|  
|<span data-ttu-id="ca66b-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-122">TABLE_TYPE</span></span>|<span data-ttu-id="ca66b-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-123">String</span></span>|  
|<span data-ttu-id="ca66b-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-124">REMARKS</span></span>|<span data-ttu-id="ca66b-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="ca66b-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="ca66b-126">Indexes</span></span>  
  
|<span data-ttu-id="ca66b-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-127">ColumnName</span></span>|<span data-ttu-id="ca66b-128">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-129">TABLE_CAT</span></span>|<span data-ttu-id="ca66b-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-130">String</span></span>|  
|<span data-ttu-id="ca66b-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-131">TABLE_SCHEM</span></span>|<span data-ttu-id="ca66b-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-132">String</span></span>|  
|<span data-ttu-id="ca66b-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-133">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-134">String</span></span>|  
|<span data-ttu-id="ca66b-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="ca66b-135">NON_UNIQUE</span></span>|<span data-ttu-id="ca66b-136">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-136">Int16</span></span>|  
|<span data-ttu-id="ca66b-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="ca66b-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-138">String</span></span>|  
|<span data-ttu-id="ca66b-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-139">INDEX_NAME</span></span>|<span data-ttu-id="ca66b-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-140">String</span></span>|  
|<span data-ttu-id="ca66b-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-141">TYPE</span></span>|<span data-ttu-id="ca66b-142">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-142">Int16</span></span>|  
|<span data-ttu-id="ca66b-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-144">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-144">Int16</span></span>|  
|<span data-ttu-id="ca66b-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-145">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-146">String</span></span>|  
|<span data-ttu-id="ca66b-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="ca66b-147">ASC_OR_DESC</span></span>|<span data-ttu-id="ca66b-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-148">String</span></span>|  
|<span data-ttu-id="ca66b-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="ca66b-149">CARDINATLITY</span></span>|<span data-ttu-id="ca66b-150">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-150">Int32</span></span>|  
|<span data-ttu-id="ca66b-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="ca66b-151">PAGES</span></span>|<span data-ttu-id="ca66b-152">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-152">Int32</span></span>|  
|<span data-ttu-id="ca66b-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-153">FILTER_CONDITION</span></span>|<span data-ttu-id="ca66b-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-154">String</span></span>|  
|<span data-ttu-id="ca66b-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ca66b-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ca66b-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-156">String</span></span>|  
|<span data-ttu-id="ca66b-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-158">Byte</span><span class="sxs-lookup"><span data-stu-id="ca66b-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ca66b-159">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-159">Columns</span></span>  
  
|<span data-ttu-id="ca66b-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-160">ColumnName</span></span>|<span data-ttu-id="ca66b-161">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-162">TABLE_CAT</span></span>|<span data-ttu-id="ca66b-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-163">String</span></span>|  
|<span data-ttu-id="ca66b-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-164">TABLE_SCHEM</span></span>|<span data-ttu-id="ca66b-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-165">String</span></span>|  
|<span data-ttu-id="ca66b-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-166">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-167">String</span></span>|  
|<span data-ttu-id="ca66b-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-168">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-169">String</span></span>|  
|<span data-ttu-id="ca66b-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-170">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-171">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-171">Int16</span></span>|  
|<span data-ttu-id="ca66b-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-172">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-173">String</span></span>|  
|<span data-ttu-id="ca66b-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ca66b-174">COLUMN_SIZE</span></span>|<span data-ttu-id="ca66b-175">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-175">Int32</span></span>|  
|<span data-ttu-id="ca66b-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="ca66b-177">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-177">Int32</span></span>|  
|<span data-ttu-id="ca66b-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ca66b-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ca66b-179">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-179">Int16</span></span>|  
|<span data-ttu-id="ca66b-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ca66b-181">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-181">Int16</span></span>|  
|<span data-ttu-id="ca66b-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-182">NULLABLE</span></span>|<span data-ttu-id="ca66b-183">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-183">Int16</span></span>|  
|<span data-ttu-id="ca66b-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-184">REMARKS</span></span>|<span data-ttu-id="ca66b-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-185">String</span></span>|  
|<span data-ttu-id="ca66b-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ca66b-186">COLUMN_DEF</span></span>|<span data-ttu-id="ca66b-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-187">String</span></span>|  
|<span data-ttu-id="ca66b-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-189">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-189">Int16</span></span>|  
|<span data-ttu-id="ca66b-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ca66b-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ca66b-191">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-191">Int16</span></span>|  
|<span data-ttu-id="ca66b-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ca66b-193">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-193">Int32</span></span>|  
|<span data-ttu-id="ca66b-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-195">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-195">Int32</span></span>|  
|<span data-ttu-id="ca66b-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-196">IS_NULLABLE</span></span>|<span data-ttu-id="ca66b-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-197">String</span></span>|  
|<span data-ttu-id="ca66b-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ca66b-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ca66b-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-199">String</span></span>|  
|<span data-ttu-id="ca66b-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ca66b-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ca66b-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-201">String</span></span>|  
|<span data-ttu-id="ca66b-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-203">Byte</span><span class="sxs-lookup"><span data-stu-id="ca66b-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ca66b-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-204">Procedures</span></span>  
  
|<span data-ttu-id="ca66b-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-205">ColumnName</span></span>|<span data-ttu-id="ca66b-206">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="ca66b-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-208">String</span></span>|  
|<span data-ttu-id="ca66b-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ca66b-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-210">String</span></span>|  
|<span data-ttu-id="ca66b-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-212">String</span></span>|  
|<span data-ttu-id="ca66b-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-214">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-214">Int32</span></span>|  
|<span data-ttu-id="ca66b-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-216">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-216">Int32</span></span>|  
|<span data-ttu-id="ca66b-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ca66b-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ca66b-218">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-218">Int32</span></span>|  
|<span data-ttu-id="ca66b-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-219">REMARKS</span></span>|<span data-ttu-id="ca66b-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-220">String</span></span>|  
|<span data-ttu-id="ca66b-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ca66b-222">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ca66b-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ca66b-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-224">ColumnName</span></span>|<span data-ttu-id="ca66b-225">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="ca66b-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-227">String</span></span>|  
|<span data-ttu-id="ca66b-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ca66b-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-229">String</span></span>|  
|<span data-ttu-id="ca66b-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-231">String</span></span>|  
|<span data-ttu-id="ca66b-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-232">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-233">String</span></span>|  
|<span data-ttu-id="ca66b-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-234">COLUMN_TYPE</span></span>|<span data-ttu-id="ca66b-235">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-235">Int16</span></span>|  
|<span data-ttu-id="ca66b-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-236">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-237">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-237">Int16</span></span>|  
|<span data-ttu-id="ca66b-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-238">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-239">String</span></span>|  
|<span data-ttu-id="ca66b-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ca66b-240">COLUMN_SIZE</span></span>|<span data-ttu-id="ca66b-241">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-241">Int32</span></span>|  
|<span data-ttu-id="ca66b-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="ca66b-243">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-243">Int32</span></span>|  
|<span data-ttu-id="ca66b-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ca66b-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ca66b-245">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-245">Int16</span></span>|  
|<span data-ttu-id="ca66b-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ca66b-247">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-247">Int16</span></span>|  
|<span data-ttu-id="ca66b-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-248">NULLABLE</span></span>|<span data-ttu-id="ca66b-249">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-249">Int16</span></span>|  
|<span data-ttu-id="ca66b-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-250">REMARKS</span></span>|<span data-ttu-id="ca66b-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-251">String</span></span>|  
|<span data-ttu-id="ca66b-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ca66b-252">COLUMN_DEF</span></span>|<span data-ttu-id="ca66b-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-253">String</span></span>|  
|<span data-ttu-id="ca66b-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-255">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-255">Int16</span></span>|  
|<span data-ttu-id="ca66b-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ca66b-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ca66b-257">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-257">Int16</span></span>|  
|<span data-ttu-id="ca66b-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ca66b-259">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-259">Int32</span></span>|  
|<span data-ttu-id="ca66b-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-261">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-261">Int32</span></span>|  
|<span data-ttu-id="ca66b-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-262">IS_NULLABLE</span></span>|<span data-ttu-id="ca66b-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-263">String</span></span>|  
|<span data-ttu-id="ca66b-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ca66b-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ca66b-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-265">String</span></span>|  
|<span data-ttu-id="ca66b-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ca66b-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ca66b-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-267">String</span></span>|  
|<span data-ttu-id="ca66b-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-269">Byte</span><span class="sxs-lookup"><span data-stu-id="ca66b-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="ca66b-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ca66b-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="ca66b-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-271">ColumnName</span></span>|<span data-ttu-id="ca66b-272">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="ca66b-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-274">String</span></span>|  
|<span data-ttu-id="ca66b-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ca66b-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-276">String</span></span>|  
|<span data-ttu-id="ca66b-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-278">String</span></span>|  
|<span data-ttu-id="ca66b-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-279">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-280">String</span></span>|  
|<span data-ttu-id="ca66b-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-281">COLUMN_TYPE</span></span>|<span data-ttu-id="ca66b-282">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-282">Int16</span></span>|  
|<span data-ttu-id="ca66b-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-283">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-284">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-284">Int16</span></span>|  
|<span data-ttu-id="ca66b-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-285">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-286">String</span></span>|  
|<span data-ttu-id="ca66b-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ca66b-287">COLUMN_SIZE</span></span>|<span data-ttu-id="ca66b-288">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-288">Int32</span></span>|  
|<span data-ttu-id="ca66b-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="ca66b-290">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-290">Int32</span></span>|  
|<span data-ttu-id="ca66b-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ca66b-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ca66b-292">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-292">Int16</span></span>|  
|<span data-ttu-id="ca66b-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ca66b-294">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-294">Int16</span></span>|  
|<span data-ttu-id="ca66b-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-295">NULLABLE</span></span>|<span data-ttu-id="ca66b-296">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-296">Int16</span></span>|  
|<span data-ttu-id="ca66b-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-297">REMARKS</span></span>|<span data-ttu-id="ca66b-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-298">String</span></span>|  
|<span data-ttu-id="ca66b-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ca66b-299">COLUMN_DEF</span></span>|<span data-ttu-id="ca66b-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-300">String</span></span>|  
|<span data-ttu-id="ca66b-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-302">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-302">Int16</span></span>|  
|<span data-ttu-id="ca66b-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ca66b-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ca66b-304">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-304">Int16</span></span>|  
|<span data-ttu-id="ca66b-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ca66b-306">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-306">Int32</span></span>|  
|<span data-ttu-id="ca66b-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-308">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-308">Int32</span></span>|  
|<span data-ttu-id="ca66b-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-309">IS_NULLABLE</span></span>|<span data-ttu-id="ca66b-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-310">String</span></span>|  
|<span data-ttu-id="ca66b-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ca66b-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="ca66b-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-312">String</span></span>|  
|<span data-ttu-id="ca66b-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ca66b-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="ca66b-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-314">String</span></span>|  
|<span data-ttu-id="ca66b-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-316">Byte</span><span class="sxs-lookup"><span data-stu-id="ca66b-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="ca66b-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="ca66b-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="ca66b-318">Microsoft SQL Server Oracle ODBC-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="ca66b-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ca66b-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="ca66b-319">Tables</span></span>  
  
-   <span data-ttu-id="ca66b-320">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-320">Columns</span></span>  
  
-   <span data-ttu-id="ca66b-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-321">Procedures</span></span>  
  
-   <span data-ttu-id="ca66b-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ca66b-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ca66b-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ca66b-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="ca66b-324">Views</span></span>  
  
-   <span data-ttu-id="ca66b-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="ca66b-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ca66b-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="ca66b-326">Tables and Views</span></span>  
  
|<span data-ttu-id="ca66b-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-327">ColumnName</span></span>|<span data-ttu-id="ca66b-328">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-330">String</span></span>|  
|<span data-ttu-id="ca66b-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-331">TABLE_OWNER</span></span>|<span data-ttu-id="ca66b-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-332">String</span></span>|  
|<span data-ttu-id="ca66b-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-333">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-334">String</span></span>|  
|<span data-ttu-id="ca66b-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-335">TABLE_TYPE</span></span>|<span data-ttu-id="ca66b-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-336">String</span></span>|  
|<span data-ttu-id="ca66b-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-337">REMARKS</span></span>|<span data-ttu-id="ca66b-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ca66b-339">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-339">Columns</span></span>  
  
|<span data-ttu-id="ca66b-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-340">ColumnName</span></span>|<span data-ttu-id="ca66b-341">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-343">String</span></span>|  
|<span data-ttu-id="ca66b-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-344">TABLE_OWNER</span></span>|<span data-ttu-id="ca66b-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-345">String</span></span>|  
|<span data-ttu-id="ca66b-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-346">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-347">String</span></span>|  
|<span data-ttu-id="ca66b-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-348">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-349">String</span></span>|  
|<span data-ttu-id="ca66b-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-350">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-351">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-351">Int16</span></span>|  
|<span data-ttu-id="ca66b-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-352">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-353">String</span></span>|  
|<span data-ttu-id="ca66b-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ca66b-354">PRECISION</span></span>|<span data-ttu-id="ca66b-355">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-355">Int32</span></span>|  
|<span data-ttu-id="ca66b-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-356">LENGTH</span></span>|<span data-ttu-id="ca66b-357">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-357">Int32</span></span>|  
|<span data-ttu-id="ca66b-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="ca66b-358">SCALE</span></span>|<span data-ttu-id="ca66b-359">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-359">Int16</span></span>|  
|<span data-ttu-id="ca66b-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-360">RADIX</span></span>|<span data-ttu-id="ca66b-361">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-361">Int16</span></span>|  
|<span data-ttu-id="ca66b-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-362">NULLABLE</span></span>|<span data-ttu-id="ca66b-363">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-363">Int16</span></span>|  
|<span data-ttu-id="ca66b-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-364">REMARKS</span></span>|<span data-ttu-id="ca66b-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-365">String</span></span>|  
|<span data-ttu-id="ca66b-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-367">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ca66b-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-368">Procedures</span></span>  
  
|<span data-ttu-id="ca66b-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-369">ColumnName</span></span>|<span data-ttu-id="ca66b-370">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-372">String</span></span>|  
|<span data-ttu-id="ca66b-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ca66b-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-374">String</span></span>|  
|<span data-ttu-id="ca66b-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-376">String</span></span>|  
|<span data-ttu-id="ca66b-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-378">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-378">Int16</span></span>|  
|<span data-ttu-id="ca66b-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-380">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-380">Int16</span></span>|  
|<span data-ttu-id="ca66b-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ca66b-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ca66b-382">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-382">Int16</span></span>|  
|<span data-ttu-id="ca66b-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-383">REMARKS</span></span>|<span data-ttu-id="ca66b-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-384">String</span></span>|  
|<span data-ttu-id="ca66b-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ca66b-386">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ca66b-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ca66b-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-388">ColumnName</span></span>|<span data-ttu-id="ca66b-389">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-391">String</span></span>|  
|<span data-ttu-id="ca66b-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ca66b-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-393">String</span></span>|  
|<span data-ttu-id="ca66b-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-395">String</span></span>|  
|<span data-ttu-id="ca66b-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-396">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-397">String</span></span>|  
|<span data-ttu-id="ca66b-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-398">COLUMN_TYPE</span></span>|<span data-ttu-id="ca66b-399">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-399">Int16</span></span>|  
|<span data-ttu-id="ca66b-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-400">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-401">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-401">Int16</span></span>|  
|<span data-ttu-id="ca66b-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-402">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-403">String</span></span>|  
|<span data-ttu-id="ca66b-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ca66b-404">PRECISION</span></span>|<span data-ttu-id="ca66b-405">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-405">Int32</span></span>|  
|<span data-ttu-id="ca66b-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-406">LENGTH</span></span>|<span data-ttu-id="ca66b-407">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-407">Int32</span></span>|  
|<span data-ttu-id="ca66b-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="ca66b-408">SCALE</span></span>|<span data-ttu-id="ca66b-409">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-409">Int16</span></span>|  
|<span data-ttu-id="ca66b-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-410">RADIX</span></span>|<span data-ttu-id="ca66b-411">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-411">Int16</span></span>|  
|<span data-ttu-id="ca66b-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-412">NULLABLE</span></span>|<span data-ttu-id="ca66b-413">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-413">Int16</span></span>|  
|<span data-ttu-id="ca66b-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-414">REMARKS</span></span>|<span data-ttu-id="ca66b-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-415">String</span></span>|  
|<span data-ttu-id="ca66b-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ca66b-416">OVERLOAD</span></span>|<span data-ttu-id="ca66b-417">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-417">Int32</span></span>|  
|<span data-ttu-id="ca66b-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-419">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="ca66b-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="ca66b-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="ca66b-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="ca66b-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="ca66b-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="ca66b-422">Tables</span></span>  
  
-   <span data-ttu-id="ca66b-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="ca66b-423">Indexes</span></span>  
  
-   <span data-ttu-id="ca66b-424">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-424">Columns</span></span>  
  
-   <span data-ttu-id="ca66b-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-425">Procedures</span></span>  
  
-   <span data-ttu-id="ca66b-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="ca66b-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ca66b-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="ca66b-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="ca66b-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="ca66b-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="ca66b-429">Tables and Views</span></span>  
  
|<span data-ttu-id="ca66b-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-430">ColumnName</span></span>|<span data-ttu-id="ca66b-431">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-433">String</span></span>|  
|<span data-ttu-id="ca66b-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-434">TABLE_OWNER</span></span>|<span data-ttu-id="ca66b-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-435">String</span></span>|  
|<span data-ttu-id="ca66b-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-436">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-437">String</span></span>|  
|<span data-ttu-id="ca66b-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-438">TABLE_TYPE</span></span>|<span data-ttu-id="ca66b-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-439">String</span></span>|  
|<span data-ttu-id="ca66b-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-440">REMARKS</span></span>|<span data-ttu-id="ca66b-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ca66b-442">Columns</span><span class="sxs-lookup"><span data-stu-id="ca66b-442">Columns</span></span>  
  
|<span data-ttu-id="ca66b-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-443">ColumnName</span></span>|<span data-ttu-id="ca66b-444">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-446">String</span></span>|  
|<span data-ttu-id="ca66b-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-447">TABLE_OWNER</span></span>|<span data-ttu-id="ca66b-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-448">String</span></span>|  
|<span data-ttu-id="ca66b-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-449">TABLE_NAME</span></span>|<span data-ttu-id="ca66b-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-450">String</span></span>|  
|<span data-ttu-id="ca66b-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-451">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-452">String</span></span>|  
|<span data-ttu-id="ca66b-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-453">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-454">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-454">Int16</span></span>|  
|<span data-ttu-id="ca66b-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-455">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-456">String</span></span>|  
|<span data-ttu-id="ca66b-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ca66b-457">PRECISION</span></span>|<span data-ttu-id="ca66b-458">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-458">Int32</span></span>|  
|<span data-ttu-id="ca66b-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-459">LENGTH</span></span>|<span data-ttu-id="ca66b-460">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-460">Int32</span></span>|  
|<span data-ttu-id="ca66b-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="ca66b-461">SCALE</span></span>|<span data-ttu-id="ca66b-462">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-462">Int16</span></span>|  
|<span data-ttu-id="ca66b-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-463">RADIX</span></span>|<span data-ttu-id="ca66b-464">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-464">Int16</span></span>|  
|<span data-ttu-id="ca66b-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-465">NULLABLE</span></span>|<span data-ttu-id="ca66b-466">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-466">Int16</span></span>|  
|<span data-ttu-id="ca66b-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-467">REMARKS</span></span>|<span data-ttu-id="ca66b-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-468">String</span></span>|  
|<span data-ttu-id="ca66b-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-470">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ca66b-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ca66b-471">Procedures</span></span>  
  
|<span data-ttu-id="ca66b-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-472">ColumnName</span></span>|<span data-ttu-id="ca66b-473">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-475">String</span></span>|  
|<span data-ttu-id="ca66b-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ca66b-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-477">String</span></span>|  
|<span data-ttu-id="ca66b-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-479">String</span></span>|  
|<span data-ttu-id="ca66b-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-481">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-481">Int16</span></span>|  
|<span data-ttu-id="ca66b-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="ca66b-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="ca66b-483">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-483">Int16</span></span>|  
|<span data-ttu-id="ca66b-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="ca66b-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="ca66b-485">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-485">Int16</span></span>|  
|<span data-ttu-id="ca66b-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-486">REMARKS</span></span>|<span data-ttu-id="ca66b-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-487">String</span></span>|  
|<span data-ttu-id="ca66b-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="ca66b-489">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="ca66b-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="ca66b-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="ca66b-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-491">ColumnName</span></span>|<span data-ttu-id="ca66b-492">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="ca66b-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="ca66b-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-494">String</span></span>|  
|<span data-ttu-id="ca66b-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca66b-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="ca66b-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-496">String</span></span>|  
|<span data-ttu-id="ca66b-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-498">String</span></span>|  
|<span data-ttu-id="ca66b-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-499">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-500">String</span></span>|  
|<span data-ttu-id="ca66b-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-501">COLUMN_TYPE</span></span>|<span data-ttu-id="ca66b-502">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-502">Int16</span></span>|  
|<span data-ttu-id="ca66b-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-503">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-504">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-504">Int16</span></span>|  
|<span data-ttu-id="ca66b-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-505">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-506">String</span></span>|  
|<span data-ttu-id="ca66b-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="ca66b-507">PRECISION</span></span>|<span data-ttu-id="ca66b-508">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-508">Int32</span></span>|  
|<span data-ttu-id="ca66b-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-509">LENGTH</span></span>|<span data-ttu-id="ca66b-510">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-510">Int32</span></span>|  
|<span data-ttu-id="ca66b-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="ca66b-511">SCALE</span></span>|<span data-ttu-id="ca66b-512">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-512">Int16</span></span>|  
|<span data-ttu-id="ca66b-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-513">RADIX</span></span>|<span data-ttu-id="ca66b-514">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-514">Int16</span></span>|  
|<span data-ttu-id="ca66b-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-515">NULLABLE</span></span>|<span data-ttu-id="ca66b-516">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-516">Int16</span></span>|  
|<span data-ttu-id="ca66b-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-517">REMARKS</span></span>|<span data-ttu-id="ca66b-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-518">String</span></span>|  
|<span data-ttu-id="ca66b-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="ca66b-519">OVERLOAD</span></span>|<span data-ttu-id="ca66b-520">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-520">Int32</span></span>|  
|<span data-ttu-id="ca66b-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-522">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="ca66b-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ca66b-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="ca66b-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ca66b-524">ColumnName</span></span>|<span data-ttu-id="ca66b-525">DataType</span><span class="sxs-lookup"><span data-stu-id="ca66b-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="ca66b-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="ca66b-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="ca66b-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-527">String</span></span>|  
|<span data-ttu-id="ca66b-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="ca66b-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="ca66b-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-529">String</span></span>|  
|<span data-ttu-id="ca66b-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="ca66b-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-531">String</span></span>|  
|<span data-ttu-id="ca66b-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-532">COLUMN_NAME</span></span>|<span data-ttu-id="ca66b-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-533">String</span></span>|  
|<span data-ttu-id="ca66b-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-534">COLUMN_TYPE</span></span>|<span data-ttu-id="ca66b-535">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-535">Int16</span></span>|  
|<span data-ttu-id="ca66b-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-536">DATA_TYPE</span></span>|<span data-ttu-id="ca66b-537">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-537">Int16</span></span>|  
|<span data-ttu-id="ca66b-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="ca66b-538">TYPE_NAME</span></span>|<span data-ttu-id="ca66b-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-539">String</span></span>|  
|<span data-ttu-id="ca66b-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="ca66b-540">COLUMN_SIZE</span></span>|<span data-ttu-id="ca66b-541">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-541">Int32</span></span>|  
|<span data-ttu-id="ca66b-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="ca66b-543">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-543">Int32</span></span>|  
|<span data-ttu-id="ca66b-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="ca66b-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="ca66b-545">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-545">Int16</span></span>|  
|<span data-ttu-id="ca66b-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="ca66b-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="ca66b-547">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-547">Int16</span></span>|  
|<span data-ttu-id="ca66b-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-548">NULLABLE</span></span>|<span data-ttu-id="ca66b-549">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-549">Int16</span></span>|  
|<span data-ttu-id="ca66b-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="ca66b-550">REMARKS</span></span>|<span data-ttu-id="ca66b-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-551">String</span></span>|  
|<span data-ttu-id="ca66b-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="ca66b-552">COLUMN_DEF</span></span>|<span data-ttu-id="ca66b-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-553">String</span></span>|  
|<span data-ttu-id="ca66b-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="ca66b-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="ca66b-555">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-555">Int16</span></span>|  
|<span data-ttu-id="ca66b-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="ca66b-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="ca66b-557">Int16</span><span class="sxs-lookup"><span data-stu-id="ca66b-557">Int16</span></span>|  
|<span data-ttu-id="ca66b-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="ca66b-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="ca66b-559">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-559">Int32</span></span>|  
|<span data-ttu-id="ca66b-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="ca66b-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="ca66b-561">Int32</span><span class="sxs-lookup"><span data-stu-id="ca66b-561">Int32</span></span>|  
|<span data-ttu-id="ca66b-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="ca66b-562">IS_NULLABLE</span></span>|<span data-ttu-id="ca66b-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ca66b-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca66b-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca66b-564">See Also</span></span>  
 [<span data-ttu-id="ca66b-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ca66b-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
