**Listar consultas agendadas para hoje**



SELECT 

Consulta.ID, 

Consulta.Data\_Hora,

Paciente.Nome,

Medico.Nome

From Consulta

JOIN Paciente ON Consulta.Paciente\_ID = Paciente.ID

JOIN Medico ON Consulta.Medico\_ID = Medico.ID

WHERE DATE(Consulta.Data\_Hora) = CURDATE();





---------------------------------------------------------



**Contar internações para o quarto**



SELECT Quarto, COUNT(\*)

FROM Internação

GROUP BY Quarto;



---------------------------------------------------------



**Relatório de prescrições por medicamento**



SELECT Medicamento.Nome, SUM(Pescrição.Quantidade)
FROM Prescrição
JOIN Medicamentos ON Prescrição.MedicamentoID = Medicamento.ID
GROUP BY Medicamento.Nome;













