Changelog
=========

All notable changes to `pyroomacoustics
<https://github.com/LCAV/pyroomacoustics>`_ will be documented in this file.

The format is based on `Keep a
Changelog <http://keepachangelog.com/en/1.0.0/>`__ and this project
adheres to `Semantic Versioning <http://semver.org/spec/v2.0.0.html>`_.

`Unreleased`_
-------------

Added
~~~~~

- Added noise reduction sub-package ``denoise`` with spectral subtraction
  class and example.
- Renamed ``realtime`` to ``transform`` and added deprecation warning.
- Added a cython function to efficiently compute the fractional delays in the room
  impulse response from time delays and attenuations
- `notebooks` folder.
- Demo IPython notebook (with WAV files) of several features of the package.
- Wrapper for Google's Speech Command Dataset and an example usage script in ``examples``.
- Lots of new features in the ``pyroomacoustics.realtime`` subpackage

  * The ``STFT`` class can now be used both for frame-by-frame processing
    or for bulk processing
  * The functionality will replace the methods ``pyroomacoustics.stft``,
    ``pyroomacoustics.istft``, ``pyroomacoustics.overlap_add``, etc,
  * The **new** function ``pyroomacoustics.realtime.compute_synthesis_window``
    computes the optimal synthesis window given an analysis window and
    the frame shift
  * Extensive tests for the ``pyroomacoustics.realtime`` module
  * Convenience functions ``pyroomacoustics.realtime.analysis`` and
    ``pyroomacoustics.realtime.synthesis`` with an interface similar
    to ``pyroomacoustics.stft`` and ``pyroomacoustics.istft`` (which
    are now deprecated and will disappear soon)
  * The ordering of axis in the output from bulk STFT is now
    ``(n_frames, n_frequencies, n_channels)``
  * Support for Intel's ``mkl_fft`` `package <https://github.com/IntelPython/mkl_fft>`_
  * ``axis`` (along which to perform DFT) and ``bits`` parameters for ``DFT`` class.

Changed
~~~~~~~

- Using now the built-in RIR generator in `examples/doa_algorithms.py`
- Improved the download/uncompress function for large datasets
- Dusted the code for plotting on the sphere in ``pyroomacoustics.doa.grid.GridSphere``

Deprecation Notice
~~~~~~~~~~~~~~~~~~

- The methods ``pyroomacoustics.stft``, ``pyroomacoustics.istft``,
  ``pyroomacoustics.overlap_add``, etc, are now **deprecated**
  and will be removed in the near future

`0.1.18`_ - 2018-04-24
----------------------

Added
~~~~~

- Added AuxIVA (independent vector analysis) to ``bss`` subpackage.
- Added BSS IVA example

Changed
~~~~~~~

- Moved Trinicon blind source separation algorithm to ``bss`` subpackage.

Bugfix
~~~~~~

- Correct a bug that causes 1st order sources to be generated for `max_order==0`
  in pure python code

`0.1.17`_ - 2018-03-23
----------------------

Bugfix
~~~~~~

- Fixed issue #22 on github. Added INCREF before returning Py_None in C extension.

`0.1.16`_ - 2018-03-06
----------------------

Added
~~~~~

- Base classes for Dataset and Sample in ``pyroomacoustics.datasets``
- Methods to filter datasets according to the metadata of samples
- Deprecation warning for the TimitCorpus interface

Changed
~~~~~~~

- Add list of speakers and sentences from CMU ARCTIC
- CMUArcticDatabase basedir is now the top directory where CMU_ARCTIC database
  should be saved. Not the directory above as it previously was.
- Libroom C extension is now a proper package. It can be imported.
- Libroom C extension now compiles on windows with python>=3.5.


`0.1.15`_ - 2018-02-23
----------------------

Bugfix
~~~~~~

- Added ``pyroomacoustics.datasets`` to list of sub-packages in ``setup.py``


`0.1.14`_ - 2018-02-20
----------------------

Added
~~~~~

-  Changelog
-  CMU ARCTIC corpus wrapper in ``pyroomacoustics.datasets``

Changed
~~~~~~~

-  Moved TIMIT corpus wrapper from ``pyroomacoustics.recognition`` module to sub-package
   ``pyroomacoustics.datasets.timit``


.. _Unreleased: https://github.com/LCAV/pyroomacoustics/compare/v0.1.18...HEAD
.. _0.1.18: https://github.com/LCAV/pyroomacoustics/compare/v0.1.17...v0.1.18
.. _0.1.17: https://github.com/LCAV/pyroomacoustics/compare/v0.1.16...v0.1.17
.. _0.1.16: https://github.com/LCAV/pyroomacoustics/compare/v0.1.15...v0.1.16
.. _0.1.15: https://github.com/LCAV/pyroomacoustics/compare/v0.1.14...v0.1.15
.. _0.1.14: https://github.com/LCAV/pyroomacoustics/compare/v0.1.13...v0.1.14
