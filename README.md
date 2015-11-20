
Imports System.Data.SqlClient
Public Class Form1

    Private Sub Search_Click(sender As Object, e As EventArgs)

    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        ' If RadioButton1.Checked = True Then
        ' For i As Integer = 1944 To 2013
        Dim MyConnection As System.Data.OleDb.OleDbConnection
        Dim DtSet As System.Data.DataSet
        Dim MyCommand As System.Data.OleDb.OleDbDataAdapter




        'MsgBox(i)

        MyConnection = New System.Data.OleDb.OleDbConnection("provider=Microsoft.Jet.OLEDB.4.0;Data Source='C:\Users\Administrator\Downloads\baby1944_2013\BabyNames1944_2013\female_cy1946_top.csv';Extended Properties=Excel 8.0 ;")
        MyCommand = New System.Data.OleDb.OleDbDataAdapter("select * from [female_cy1946_top$]", MyConnection)

        MyCommand.TableMappings.Add("Table", "testtable")
        DtSet = New System.Data.DataSet
        'MsgBox(i)
        MyCommand.Fill(DtSet)
        DataGridView1.DataSource = DtSet.Tables(0)


        MyConnection.Close()

        'Next
        ' End If

    End Sub
End Class
