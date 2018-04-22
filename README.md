# Traf

Traf is a proof tree viewer which cooperate with a proof assistant Coq and controlled through Proof General (PG). You are not required to obtain any knowledge to use Traf. You do not have to pay attention to it while proving lemmas by using PG. Traf automatically draws a proof tree corresponding to what you have done while you are interacting with Coq through PG. The trees drawn by Traf are informative and will be of great help.

Traf is an extention to a proof tree viewer named Prooftree. Traf version 0.1 is based on Prooftree-0.13.

Traf version 0.1 has been developed by Hideyuki Kawabata and Yuta Tanaka, with Yuuki Sasaki and Mai Kimura.


Requirements:

- Coq 8.4 or 8.6 (8.7 is not supported yet)
- Proof General 4.4.1pre (older versions such as ver 3 can be used but slight modification of PG is required)
- Lablgtk 2.18.5
- OCaml 4.05.0

###Installation

1. Obtain prooftree-0.13.tar.gz and check files. 

 `$ tar zxfv prooftree-0.13.tar.gz`

2. Put additional files and a patch file in the directory.

 `$ tar zxfv traf-0.1-patch.tar.gz`

3. Apply the patch for Traf.
  
  `$ cd prooftree-0.13`
  `$ patch -p1 < the_patch_file`

4. Build.

  `$ ./configure`

  `$ make`
  
  `$ make install` (optional)

 
###Settings
 Put following lines in `.emacs`.

  `(setq coq-prog-name "/somewhere/coqtop")`
  `(setq proof-tree-program "traf")`
  `(setq exec-path (cons "/where/traf/resides/" exec-path))`
  `(load "/somewhere/pg/is/installed/generic/proof-site")`

###Use
- While proving by using Proof General, you can invoke Traf by clicking `prooftree` icon, or equivalently, type `C-c C-d`.
- When a Theorem/Lemma/Example, etc., is finished, the connection between PG and Traf is closed. When you start proving next Theorem, invoke Traf again.