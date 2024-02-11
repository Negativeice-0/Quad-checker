package main

import (
	"fmt"
	"os"
	"os/exec"
)

func main() {
	cmd := exec.Command("./quadchecker")
	cmd.Stdin = os.Stdin
	cmd.Stdout = os.Stdout
	cmd.Stderr = os.Stderr
	err := cmd.Start()
	if err != nil {
		fmt.Println("error", err)
		return
	}

	err = cmd.Wait()
	if err != nil {
		fmt.Println("error", err)
		return
	}
}
