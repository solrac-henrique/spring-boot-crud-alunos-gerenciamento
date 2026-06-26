package com.gerenciamento.alunos.controller;

import com.gerenciamento.alunos.model.Aluno;
import com.gerenciamento.alunos.repository.AlunoRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.*;

@Controller
@RequestMapping("/")
public class AlunoController {

    @Autowired
    private AlunoRepository alunoRepository;

    // Página inicial - lista todos os alunos
    @GetMapping
    public String listarAlunos(Model model) {
        model.addAttribute("alunos", alunoRepository.findAll());
        return "index";
    }

    // Salvar novo aluno
    @PostMapping("/salvar")
    public String salvarAluno(@ModelAttribute Aluno aluno) {
        alunoRepository.save(aluno);
        return "redirect:/";
    }

    // Excluir aluno
    @GetMapping("/excluir/{id}")
    public String excluirAluno(@PathVariable Long id) {
        alunoRepository.deleteById(id);
        return "redirect:/";
    }

    // Mostrar formulário de edição
    @GetMapping("/editar/{id}")
    public String editarAluno(@PathVariable Long id, Model model) {
        Aluno aluno = alunoRepository.findById(id).orElse(null);
        model.addAttribute("aluno", aluno);
        model.addAttribute("alunos", alunoRepository.findAll());
        return "index";
    }
}
